---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recursos de DSC Archive
ms.openlocfilehash: d5ccd242d000a0907c6768f30923764be6bf20a3
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54048029"
---
# <a name="dsc-archive-resource"></a><span data-ttu-id="9b363-103">Recursos de DSC Archive</span><span class="sxs-lookup"><span data-stu-id="9b363-103">DSC Archive Resource</span></span>

> <span data-ttu-id="9b363-104">Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="9b363-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="9b363-105">El recurso Archive de la configuración de estado deseado (DSC) de Windows PowerShell ofrece un mecanismo para desempaquetar archivos de almacenamiento (.zip) en una ruta de acceso específica.</span><span class="sxs-lookup"><span data-stu-id="9b363-105">The Archive resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.zip) files at a specific path.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b363-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b363-106">Syntax</span></span>
```MOF
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
}
```

## <a name="properties"></a><span data-ttu-id="9b363-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9b363-107">Properties</span></span>

|  <span data-ttu-id="9b363-108">Propiedad</span><span class="sxs-lookup"><span data-stu-id="9b363-108">Property</span></span>  |  <span data-ttu-id="9b363-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b363-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="9b363-110">Destination</span><span class="sxs-lookup"><span data-stu-id="9b363-110">Destination</span></span>| <span data-ttu-id="9b363-111">Especifica la ubicación donde quiere garantizar que se extraiga el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="9b363-111">Specifies the location where you want to ensure the archive contents are extracted.</span></span>|
| <span data-ttu-id="9b363-112">Ruta</span><span class="sxs-lookup"><span data-stu-id="9b363-112">Path</span></span>| <span data-ttu-id="9b363-113">Especifica la ruta de acceso de origen del archivo.</span><span class="sxs-lookup"><span data-stu-id="9b363-113">Specifies the source path of the archive file.</span></span>|
| <span data-ttu-id="9b363-114">__Checksum__</span><span class="sxs-lookup"><span data-stu-id="9b363-114">__Checksum__</span></span>| <span data-ttu-id="9b363-115">Define el tipo que se usará cuando se determine si dos archivos son iguales.</span><span class="sxs-lookup"><span data-stu-id="9b363-115">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="9b363-116">Si no se especifica __Checksum__, solo se usa el nombre del archivo o directorio para la comparación.</span><span class="sxs-lookup"><span data-stu-id="9b363-116">If __Checksum__ is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="9b363-117">Los valores válidos son: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate, none (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9b363-117">Valid values include: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate, none (default).</span></span> <span data-ttu-id="9b363-118">Si especifica __Checksum__ sin __Validate__, se producirá un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="9b363-118">If you specify __Checksum__ without __Validate__, the configuration will fail.</span></span>|
| <span data-ttu-id="9b363-119">Ensure</span><span class="sxs-lookup"><span data-stu-id="9b363-119">Ensure</span></span>| <span data-ttu-id="9b363-120">Determina si se debe comprobar si existe el contenido del archivo en __Destination__.</span><span class="sxs-lookup"><span data-stu-id="9b363-120">Determines whether to check if the content of the archive exists at the __Destination__.</span></span> <span data-ttu-id="9b363-121">Establezca esta propiedad en __Present__ para asegurarse de que el contenido exista.</span><span class="sxs-lookup"><span data-stu-id="9b363-121">Set this property to __Present__ to ensure the contents exist.</span></span> <span data-ttu-id="9b363-122">Establézcala en __Absent__ para asegurarse de que no exista.</span><span class="sxs-lookup"><span data-stu-id="9b363-122">Set it to __Absent__ to ensure they do not exist.</span></span> <span data-ttu-id="9b363-123">El valor predeterminado es __Present__.</span><span class="sxs-lookup"><span data-stu-id="9b363-123">The default value is __Present__.</span></span>|
| <span data-ttu-id="9b363-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="9b363-124">DependsOn</span></span> | <span data-ttu-id="9b363-125">Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso.</span><span class="sxs-lookup"><span data-stu-id="9b363-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="9b363-126">Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es ResourceName y su tipo es __ResourceType__, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="9b363-126">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="9b363-127">Validar</span><span class="sxs-lookup"><span data-stu-id="9b363-127">Validate</span></span>| <span data-ttu-id="9b363-128">Utiliza la propiedad Checksum para determinar si el archivo coincide con la firma.</span><span class="sxs-lookup"><span data-stu-id="9b363-128">Uses the Checksum property to determine if the archive matches the signature.</span></span> <span data-ttu-id="9b363-129">Si especifica Checksum sin Validate, se producirá un error de configuración.</span><span class="sxs-lookup"><span data-stu-id="9b363-129">If you specify Checksum without Validate, the configuration will fail.</span></span> <span data-ttu-id="9b363-130">Si especifica Validate sin Checksum, se usará una suma de comprobación SHA-256 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9b363-130">If you specify Validate without Checksum, a SHA-256 checksum is used by default.</span></span>|
| <span data-ttu-id="9b363-131">Force</span><span class="sxs-lookup"><span data-stu-id="9b363-131">Force</span></span>| <span data-ttu-id="9b363-132">Determinadas operaciones de archivos (por ejemplo, sobrescribir un archivo o eliminar un directorio que no está vacío) provocarán un error.</span><span class="sxs-lookup"><span data-stu-id="9b363-132">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="9b363-133">Si se usa la propiedad Force, se invalidan estos errores.</span><span class="sxs-lookup"><span data-stu-id="9b363-133">Using the Force property overrides such errors.</span></span> <span data-ttu-id="9b363-134">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="9b363-134">The default value is False.</span></span>|

## <a name="example"></a><span data-ttu-id="9b363-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b363-135">Example</span></span>

<span data-ttu-id="9b363-136">En el ejemplo siguiente se muestra cómo usar el recurso Archive para asegurarse de que el contenido de un archivo llamado Test.zip exista y se extraiga en un destino determinado.</span><span class="sxs-lookup"><span data-stu-id="9b363-136">The following example shows how to use the Archive resource to ensure that the contents of an archive file called Test.zip exist and are extracted at a given destination.</span></span>

```
Archive ArchiveExample {
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```