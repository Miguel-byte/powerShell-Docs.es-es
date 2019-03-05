---
title: Ejemplo StopProcessSample01 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bed607-369b-4507-87fa-f6011c2f1970
caps.latest.revision: 9
ms.openlocfilehash: f601bcd5cc57ce9828338676bf71cbe235593b5d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857141"
---
# <a name="stopprocesssample01-sample"></a><span data-ttu-id="817b1-102">Ejemplo StopProcessSample01</span><span class="sxs-lookup"><span data-stu-id="817b1-102">StopProcessSample01 Sample</span></span>

<span data-ttu-id="817b1-103">Este ejemplo muestra cómo escribir un cmdlet que solicita comentarios del usuario antes de intentar detener un proceso y cómo implementar un `PassThru` que indica que el usuario desea que el cmdlet para devolver un objeto de parámetro.</span><span class="sxs-lookup"><span data-stu-id="817b1-103">This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter indicating that the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="817b1-104">Este cmdlet es similar a la `Stop-Process` cmdlet proporcionado por Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="817b1-104">This cmdlet is similar to the `Stop-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

### <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="817b1-105">Cómo generar el ejemplo mediante Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="817b1-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="817b1-106">Con Windows PowerShell 2.0 instalado el SDK, vaya a la carpeta StopProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="817b1-106">With the Windows PowerShell 2.0 SDK installed, navigate to the StopProcessSample01 folder.</span></span> <span data-ttu-id="817b1-107">La ubicación predeterminada es C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="817b1-107">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span></span>

2. <span data-ttu-id="817b1-108">Haga doble clic en el icono del archivo de solución (.sln).</span><span class="sxs-lookup"><span data-stu-id="817b1-108">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="817b1-109">Se abre el proyecto de ejemplo en Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="817b1-109">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="817b1-110">En el **compilar** menú, seleccione **compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="817b1-110">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="817b1-111">En las carpetas \bin o \bin\debug de forma predeterminada, se compilará la biblioteca para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="817b1-111">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="817b1-112">Cómo ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="817b1-112">How to run the sample</span></span>

1. <span data-ttu-id="817b1-113">Cree la siguiente carpeta del módulo:</span><span class="sxs-lookup"><span data-stu-id="817b1-113">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/StopProcessSample01`

2. <span data-ttu-id="817b1-114">Copie el ensamblado de ejemplo en la carpeta del módulo.</span><span class="sxs-lookup"><span data-stu-id="817b1-114">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="817b1-115">Inicie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="817b1-115">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="817b1-116">Ejecute el siguiente comando para cargar el ensamblado en Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="817b1-116">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module stopprossessample01`

5. <span data-ttu-id="817b1-117">Ejecute el siguiente comando para ejecutar el cmdlet:</span><span class="sxs-lookup"><span data-stu-id="817b1-117">Run the following command to run the cmdlet:</span></span>

    `stop-proc`

## <a name="requirements"></a><span data-ttu-id="817b1-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="817b1-118">Requirements</span></span>

<span data-ttu-id="817b1-119">Este ejemplo requiere Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="817b1-119">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="817b1-120">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="817b1-120">Demonstrates</span></span>

<span data-ttu-id="817b1-121">Este ejemplo muestra lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="817b1-121">This sample demonstrates the following.</span></span>

- <span data-ttu-id="817b1-122">Declarar una clase de cmdlet mediante el atributo de Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="817b1-122">Declaring a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="817b1-123">Declarar parámetros de un cmdlet con el atributo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="817b1-123">Declaring a cmdlet parameters by using the Parameter attribute.</span></span>

- <span data-ttu-id="817b1-124">Llamar al método ShouldProcess para solicitar confirmación.</span><span class="sxs-lookup"><span data-stu-id="817b1-124">Calling the ShouldProcess method to request confirmation.</span></span>

- <span data-ttu-id="817b1-125">Implementar un `PassThru` parámetro que indica si el usuario desea que el cmdlet para devolver un objeto.</span><span class="sxs-lookup"><span data-stu-id="817b1-125">Implementing a `PassThru` parameter that indicates if the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="817b1-126">De forma predeterminada, este cmdlet no devuelve un objeto a la canalización.</span><span class="sxs-lookup"><span data-stu-id="817b1-126">By default, this cmdlet does not return an object to the pipeline.</span></span>

## <a name="example"></a><span data-ttu-id="817b1-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="817b1-127">Example</span></span>

<span data-ttu-id="817b1-128">En este ejemplo se muestra cómo implementar un `PassThru` parámetro que indica que el usuario desea que el cmdlet para devolver un objeto, y cómo solicitar comentarios de los usuarios por las llamadas a la `ShouldProcess` y `ShouldContinue` métodos.</span><span class="sxs-lookup"><span data-stu-id="817b1-128">This sample shows how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object, and how to request user feedback by calls to the `ShouldProcess` and `ShouldContinue` methods.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Collections;
using Win32Exception = System.ComponentModel.Win32Exception;
using System.Management.Automation;    // Windows PowerShell namespace
using System.Globalization;

namespace Microsoft.Samples.PowerShell.Commands
{
   #region StopProcCommand

    /// <summary>
   /// This class implements the stop-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsLifecycle.Stop, "Proc",
       SupportsShouldProcess = true)]
   public class StopProcCommand : Cmdlet
   {
       #region Parameters

      /// <summary>
      /// This parameter provides the list of process names on
      /// which the Stop-Proc cmdlet will work.
      /// </summary>
       [Parameter(
          Position = 0,
          Mandatory = true,
          ValueFromPipeline = true,
          ValueFromPipelineByPropertyName = true
       )]
       public string[] Name
       {
           get { return processNames; }
           set { processNames = value; }
       }
       private string[] processNames;

       /// <summary>
       /// This parameter overrides the ShouldContinue call to force
       /// the cmdlet to stop its operation. This parameter should always
       /// be used with caution.
       /// </summary>
       [Parameter]
       public SwitchParameter Force
       {
           get { return force; }
           set { force = value; }
       }
       private bool force;

       /// <summary>
       /// This parameter indicates that the cmdlet should return
       /// an object to the pipeline after the processing has been
       /// completed.
       /// </summary>
       [Parameter]
       public SwitchParameter PassThru
       {
           get { return passThru; }
           set { passThru = value; }
       }
       private bool passThru;

       #endregion Parameters

       #region Cmdlet Overrides

       /// <summary>
       /// The ProcessRecord method does the following for each of the
       /// requested process names:
       /// 1) Check that the process is not a critical process.
       /// 2) Attempt to stop that process.
       /// If no process is requested then nothing occurs.
       /// </summary>
       protected override void ProcessRecord()
       {
           foreach (string name in processNames)
           {
               // For every process name passed to the cmdlet, get the associated
               // processes.
               // Write a nonterminating error for failure to retrieve
               // a process.
               Process[] processes;

               try
               {
                   processes = Process.GetProcessesByName(name);
               }
               catch (InvalidOperationException ioe)
               {
                   WriteError(new ErrorRecord(ioe,"UnableToAccessProcessByName",
                       ErrorCategory.InvalidOperation, name));

                   continue;
               }

               // Try to stop the processes that have been retrieved.
               foreach (Process process in processes)
               {
                   string processName;

                   try
                   {
                       processName = process.ProcessName;
                   }
                   catch (Win32Exception e)
                   {
                      WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                                           ErrorCategory.ReadError, process));
                      continue;
                   }

                   // Confirm the operation with the user first.
                   // This is always false if the WhatIf parameter is set.
                   if (!ShouldProcess(string.Format(CultureInfo.CurrentCulture,"{0} ({1})", processName,
                               process.Id)))
                   {
                       continue;
                   }

                   // Make sure that the user really wants to stop a critical
                   // process that culd possibly stop the computer.
                   bool criticalProcess =
                       criticalProcessNames.Contains(processName.ToLower(CultureInfo.CurrentCulture));

                   if (criticalProcess &&!force)
                   {
                       string message = String.Format
                           (CultureInfo.CurrentCulture,
                                "The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                                    processName);

                       // It is possible that the ProcessRecord method is called
                       // multiple times when objects are recieved as inputs from
                       // the pipeline. So to retain YesToAll and NoToAll input that
                       // the user may enter across mutilple calls to this function,
                       // they are stored as private members of the cmdlet.
                       if (!ShouldContinue(message, "Warning!",
                                               ref yesToAll, ref noToAll))
                       {
                           continue;
                       }
                   } // if (cricicalProcess...

                   // Stop the named process.
                   try
                   {
                       process.Kill();
                   }
                   catch (Exception e)
                   {
                       if ((e is Win32Exception) || (e is SystemException) ||
                          (e is InvalidOperationException))
                       {
                           // This process could not be stopped so write
                           // a nonterminating error.
                           WriteError(new ErrorRecord(e, "CouldNotStopProcess",
                                           ErrorCategory.CloseError, process));
                           continue;
                       } // if ((e is...
                       else throw;
                   } // catch

                   // If the PassThru parameter is
                   // specified, return the terminated process.
                   if (passThru)
                   {
                       WriteObject(process);
                   }
               } // foreach (Process...
           } // foreach (string...
       } // ProcessRecord

       #endregion Cmdlet Overrides

       #region Private Data

       private bool yesToAll, noToAll;

       /// <summary>
       /// Partial list of critical processes that should not be
       /// stopped.  Lower case is used for case insensitive matching.
       /// </summary>
       private ArrayList criticalProcessNames = new ArrayList(
          new string[] { "system", "winlogon", "spoolsv" }
       );

       #endregion Private Data

   } // StopProcCommand

   #endregion StopProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="817b1-129">Véase también</span><span class="sxs-lookup"><span data-stu-id="817b1-129">See Also</span></span>

[<span data-ttu-id="817b1-130">Escribir un cmdlet de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="817b1-130">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)