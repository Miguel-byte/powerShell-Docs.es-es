---
title: Cómo admitir trabajos | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eac452c-eae2-4193-b4da-0b618bef3677
caps.latest.revision: 9
ms.openlocfilehash: 4b3fa7a54dc4096e79c4de94c8b28f4a784d4627
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855911"
---
# <a name="how-to-support-jobs"></a>Cómo admitir trabajos

Este ejemplo muestra cómo admitir los trabajos al escribir cmdlets. Si desea que los usuarios para ejecutar el cmdlet como un trabajo en segundo plano, debe incluir el código descrito en el siguiente procedimiento. Para obtener más información acerca de los trabajos en segundo plano, vea [trabajos en segundo plano](./background-jobs.md).

## <a name="to-support-jobs"></a>Para admitir los trabajos

1. Definir un `AsJob` parámetro de modificador para que el usuario puede decidir si desea ejecutar el cmdlet como un trabajo.

    El ejemplo siguiente muestra una declaración de parámetro AsJob.

    ```csharp
    [Parameter()]
    public SwitchParameter AsJob
    {
      get { return asjob; }
      set { asjob = value; }
    }
    private bool asjob;
    ```

    <!-- TODO!!!: review snippet reference      [!CODE [msh_samplesGetProc06#GetProc06AsJobParam](msh_samplesGetProc06#GetProc06AsJobParam)]  -->

2. Crear un objeto que se deriva el [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) clase. Este objeto puede ser un objeto de trabajo personalizado o uno de los objetos de trabajo proporcionados por Windows PowerShell, este tipo una [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) objeto.

    El ejemplo siguiente muestra un objeto de trabajo personalizado.

    ```csharp
    private SampleJob job = new SampleJob("Get-ProcAsJob");
    ```

    <!-- TODO!!!: review snippet reference      [!CODE [msh_samplesGetProc06#GetProc06JobObject](msh_samplesGetProc06#GetProc06JobObject)]  -->

3. En un método de procesamiento de registro, agregue un `if` instrucción para detectar si el cmdlet debe ejecutarse como un trabajo. El siguiente código utiliza el [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método.

    ```csharp
    protected override void ProcessRecord()
    {
      if (asjob)
      {
        // Add the job definition to the job repository,
        // return the job object, and then create the thread
        // used to run the job.
        JobRepository.Add(job);
        WriteObject(job);
        ThreadPool.QueueUserWorkItem(WorkItem);
      }
      else
      {
        job.ProcessJob();
        foreach (PSObject p in job.Output)
        {
          WriteObject(p);
        }
      }
    }
    ```

    <!-- TODO!!!: review snippet reference      [!CODE [msh_samplesGetProc06#GetProc06ProcessRecord](msh_samplesGetProc06#GetProc06ProcessRecord)]  -->

4. Para los objetos de trabajo personalizados, implemente la clase de trabajo.

    ```csharp
    private class SampleJob : Job
    {
      internal SampleJob(string command)
          : base(command)
      {
        SetJobState(JobState.NotStarted);
      }
      public override string StatusMessage
      {
        get { throw new NotImplementedException(); }
      }

      public override bool HasMoreData
      {
        get
        {
          return hasMoreData;
        }
      }
      private bool hasMoreData = true;

      public override string Location
      {
        get { throw new NotImplementedException(); }
      }

      public override void StopJob()
      {
        throw new NotImplementedException();
      }

      internal void ProcessJob()
      {
        SetJobState(JobState.Running);
        DoProcessLogic();
        SetJobState(JobState.Completed);
      }

      // Retrieve the processes of the local computer.
      void DoProcessLogic()
      {
        Process[] p = Process.GetProcesses();

        foreach (Process pl in p)
        {
          Output.Add(PSObject.AsPSObject(pl));
        }
        Output.Complete();
      } // End DoProcessLogic.
    } // End SampleJob class.
    ```

    <!-- TODO!!!: review snippet reference      [!CODE [msh_samplesGetProc06#GetProc06JobClass](msh_samplesGetProc06#GetProc06JobClass)]  -->

5. Si el cmdlet realiza el trabajo, llame a la [System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) método devuelva un objeto de proceso a la canalización. Si el trabajo se realiza como un trabajo, agregue trabajo secundario para el trabajo.

    ```csharp
    void DoProcessLogic(bool asJob)
    {
      Process[] p = Process.GetProcesses();

      foreach (Process pl in p)
      {
        if (!asjob)
        {
          WriteObject(pl);
        }
        else
        {
          job.ChildJobs[0].Output.Add(new PSObject(pl));
        }
      }
    } // End DoProcessLogic.
    ```

    <!-- TODO!!!: review snippet reference      [!CODE [msh_samplesGetProc06#GetProc06Output](msh_samplesGetProc06#GetProc06Output)]  -->

## <a name="example"></a>Ejemplo

El código de ejemplo siguiente muestra el código para un **Get-Proc** cmdlet que puede recuperar procesos internamente o mediante un trabajo en segundo plano.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;  // Windows PowerShell namespace.
using System.Threading;              // Thread pool namespace for posting work.
using System.Diagnostics;            // Diagnostics namespace for retrieving
                                     // process objects.

// This sample showes a cmdlet whose work can be done by the cmdlet or by using
// a background job. Background jobs are executed in their own thread,
// independent of the pipeline thread in which the cmdlet is executed.
//
// To load this cmdlet, create a module folder and copy the GetProcessSample06.dll
// assembly into the module folder. Make sure that the path to the module folder
// is added to the $PSModulePath environment variable.
// Module folder path:
//    user/documents/WindowsPowerShell/modules/GetProcessSample06
//
// To import the module, run the following command: Import-Module GetProcessSample06.
// To test the cmdlet, run the following command: Get-Proc -name <process name>
//

//
namespace Microsoft.Samples.PowerShell.Commands
{
  /// <summary>
  ///  This cmdlet retrieves process internally or returns
  ///  a job that retrieves the processes.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public sealed class GetProcCommand : PSCmdlet
  {

    #region Parameters
    /// <summary>
    /// Specify the Name parameter. This parameter accepts
    /// process names from the command line.
    /// </summary>
    [Parameter(
               Position = 0,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true)]
    [ValidateNotNullOrEmpty]
    public string[] Name
    {
      get { return processNames; }
      set { processNames = value; }
    }
    private string[] processNames;

    /// <summary>
    /// Specify the AsJob parameter. This parameter indicates
    /// whether the cmdlet should retrieve the processes internally
    /// or return a Job object that retrieves the processes.
    [Parameter()]
    public SwitchParameter AsJob
    {
      get { return asjob; }
      set { asjob = value; }
    }
    private bool asjob;

    #endregion Parameters

    #region Cmdlet Overrides

    // Create a custom job object.
    private SampleJob job = new SampleJob("Get-ProcAsJob");

    /// <summary>
    /// Determines if the processes should be retrieved
    /// internally or if a Job object should be returned.
    /// </summary>
    protected override void ProcessRecord()
    {
      if (asjob)
      {
        // Add the job definition to the job repository,
        // return the job object, and then create the thread
        // used to run the job.
        JobRepository.Add(job);
        WriteObject(job);
        ThreadPool.QueueUserWorkItem(WorkItem);
      }
      else
      {
        job.ProcessJob();
        foreach (PSObject p in job.Output)
        {
          WriteObject(p);
        }
      }
    }
    #endregion Overrides

    // Implement a custom job that derives
    // from the System.Management.Automation.Job class.
    private class SampleJob : Job
    {
      internal SampleJob(string command)
          : base(command)
      {
        SetJobState(JobState.NotStarted);
      }
      public override string StatusMessage
      {
        get { throw new NotImplementedException(); }
      }

      public override bool HasMoreData
      {
        get
        {
          return hasMoreData;
        }
      }
      private bool hasMoreData = true;

      public override string Location
      {
        get { throw new NotImplementedException(); }
      }

      public override void StopJob()
      {
        throw new NotImplementedException();
      }

      internal void ProcessJob()
      {
        SetJobState(JobState.Running);
        DoProcessLogic();
        SetJobState(JobState.Completed);
      }

      // Retrieve the processes of the local computer.
      void DoProcessLogic()
      {
        Process[] p = Process.GetProcesses();

        foreach (Process pl in p)
        {
          Output.Add(PSObject.AsPSObject(pl));
        }
        Output.Complete();
      } // End DoProcessLogic.
    } // End SampleJob class.

    void WorkItem(object dummy)
    {
       job.ProcessJob();
    }

    // Display the results of the work. If not a job,
    // process objects are returned. If a job, the
    // output is added to the job as a child job.
    void DoProcessLogic(bool asJob)
    {
      Process[] p = Process.GetProcesses();

      foreach (Process pl in p)
      {
        if (!asjob)
        {
          WriteObject(pl);
        }
        else
        {
          job.ChildJobs[0].Output.Add(new PSObject(pl));
        }
      }
    } // End DoProcessLogic.
  } //End GetProcCommand
}    void DoProcessLogic(bool asJob)
    {
      Process[] p = Process.GetProcesses();

      foreach (Process pl in p)
      {
        if (!asjob)
        {
          WriteObject(pl);
        }
        else
        {
          job.ChildJobs[0].Output.Add(new PSObject(pl));
        }
      }
    } // End DoProcessLogic.
```

<!-- TODO!!!: review snippet reference  [!CODE [msh_samplesGetProc06#GetProc06All](msh_samplesGetProc06#GetProc06All)]  -->
