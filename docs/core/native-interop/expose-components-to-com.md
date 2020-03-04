---
title: Esposizione di componenti .NET Core a COM
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: f6665e18e51af96761941e419fabc409e4b9391d
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240974"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="03228-102">Esposizione di componenti .NET Core a COM</span><span class="sxs-lookup"><span data-stu-id="03228-102">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="03228-103">In .NET Core, il processo di esposizione degli oggetti .NET a COM è stato significativamente semplificato rispetto a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03228-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="03228-104">Nel processo seguente viene illustrato come esporre una classe a COM.</span><span class="sxs-lookup"><span data-stu-id="03228-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="03228-105">Questa esercitazione illustra come:</span><span class="sxs-lookup"><span data-stu-id="03228-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="03228-106">Esporre una classe a COM da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03228-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="03228-107">Generare un server COM nell'ambito della creazione della libreria .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03228-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="03228-108">Generare automaticamente un manifesto del server affiancato per COM senza Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="03228-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03228-109">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="03228-109">Prerequisites</span></span>

- <span data-ttu-id="03228-110">Installare [.NET Core 3,0 SDK](https://dotnet.microsoft.com/download) o una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="03228-110">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="03228-111">Creare la libreria</span><span class="sxs-lookup"><span data-stu-id="03228-111">Create the library</span></span>

<span data-ttu-id="03228-112">Il primo passaggio consiste nel creare la libreria.</span><span class="sxs-lookup"><span data-stu-id="03228-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="03228-113">Creare una nuova cartella e in tale cartella eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="03228-113">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="03228-114">Aprire `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="03228-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="03228-115">Aggiungere `using System.Runtime.InteropServices;` all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="03228-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="03228-116">Creare un'interfaccia denominata `IServer`.</span><span class="sxs-lookup"><span data-stu-id="03228-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="03228-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03228-117">For example:</span></span>

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   [ComVisible(true)]
   [Guid(ContractGuids.ServerInterface)]
   [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
   public interface IServer
   {
       /// <summary>
       /// Compute the value of the constant Pi.
       /// </summary>
       double ComputePi();
   }
   ```

5. <span data-ttu-id="03228-118">Aggiungere l'attributo `[Guid("<IID>")]` all'interfaccia con il GUID di interfaccia per l'interfaccia COM che si sta implementando.</span><span class="sxs-lookup"><span data-stu-id="03228-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="03228-119">Ad esempio: `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="03228-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="03228-120">Si noti che questo GUID deve essere univoco perché è l'unico identificatore di questa interfaccia per COM.</span><span class="sxs-lookup"><span data-stu-id="03228-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="03228-121">In Visual Studio è possibile generare un GUID passando a Strumenti > Crea GUID per aprire lo strumento Crea GUID.</span><span class="sxs-lookup"><span data-stu-id="03228-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="03228-122">Aggiungere l'attributo `[InterfaceType]` all'interfaccia e specificare le interfacce COM di base che l'interfaccia deve implementare.</span><span class="sxs-lookup"><span data-stu-id="03228-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="03228-123">Creare una classe denominata `Server` che implementi `IServer`.</span><span class="sxs-lookup"><span data-stu-id="03228-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="03228-124">Aggiungere l'attributo `[Guid("<CLSID>")]` alla classe con il GUID dell'identificatore di classe per la classe COM che si sta implementando.</span><span class="sxs-lookup"><span data-stu-id="03228-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="03228-125">Ad esempio: `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="03228-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="03228-126">Come per il GUID dell'interfaccia, questo GUID deve essere univoco perché è l'unico identificatore di questa interfaccia per COM.</span><span class="sxs-lookup"><span data-stu-id="03228-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="03228-127">Aggiungere l'attributo `[ComVisible(true)]` sia all'interfaccia che alla classe.</span><span class="sxs-lookup"><span data-stu-id="03228-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03228-128">Diversamente da quanto avviene in .NET Framework, .NET Core richiede di specificare il CLSID di qualsiasi classe che si vuole rendere attivabile tramite COM.</span><span class="sxs-lookup"><span data-stu-id="03228-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="03228-129">Generare l'host COM</span><span class="sxs-lookup"><span data-stu-id="03228-129">Generate the COM host</span></span>

1. <span data-ttu-id="03228-130">Aprire il file di progetto `.csproj` e aggiungere `<EnableComHosting>true</EnableComHosting>` all'interno di un tag `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="03228-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="03228-131">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="03228-131">Build the project.</span></span>

<span data-ttu-id="03228-132">L'output risultante includerà un file `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` e `ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="03228-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="03228-133">Registrare l'host COM per COM</span><span class="sxs-lookup"><span data-stu-id="03228-133">Register the COM host for COM</span></span>

<span data-ttu-id="03228-134">Aprire un prompt dei comandi con privilegi elevati ed eseguire `regsvr32 ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="03228-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="03228-135">Tutti gli oggetti .NET esposti verranno così registrati in COM.</span><span class="sxs-lookup"><span data-stu-id="03228-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="03228-136">Abilitazione di COM RegFree</span><span class="sxs-lookup"><span data-stu-id="03228-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="03228-137">Aprire il file di progetto `.csproj` e aggiungere `<EnableRegFreeCom>true</EnableRegFreeCom>` all'interno di un tag `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="03228-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="03228-138">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="03228-138">Build the project.</span></span>

<span data-ttu-id="03228-139">L'output risultante includerà ora anche un file `ProjectName.X.manifest`.</span><span class="sxs-lookup"><span data-stu-id="03228-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="03228-140">Questo file è il manifesto affiancato da usare con COM senza Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="03228-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="03228-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="03228-141">Sample</span></span>

<span data-ttu-id="03228-142">È disponibile un [esempio di server COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) funzionante nel repository dotnet/samples in GitHub.</span><span class="sxs-lookup"><span data-stu-id="03228-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="03228-143">Note aggiuntive</span><span class="sxs-lookup"><span data-stu-id="03228-143">Additional notes</span></span>

<span data-ttu-id="03228-144">Diversamente da .NET Framework, in .NET Core non è disponibile alcun supporto per la generazione di una libreria dei tipi COM (TLB) da un assembly .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03228-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="03228-145">Le linee guida consentono di scrivere manualmente un file IDL o un'intestazione CC++ /per le dichiarazioni native delle interfacce com.</span><span class="sxs-lookup"><span data-stu-id="03228-145">The guidance is to either manually write an IDL file or a C/C++ header for the native declarations of the COM interfaces.</span></span>

<span data-ttu-id="03228-146">Inoltre, il caricamento di .NET Framework e .NET Core nello stesso processo ha limitazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="03228-146">Additionally, loading both .NET Framework and .NET Core into the same process does have diagnostic limitations.</span></span> <span data-ttu-id="03228-147">Il limite principale è il debug dei componenti gestiti, poiché non è possibile eseguire contemporaneamente il debug di .NET Framework e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03228-147">The primary limitation is the debugging of managed components as it is not possible to debug both .NET Framework and .NET Core at the same time.</span></span> <span data-ttu-id="03228-148">Inoltre, le due istanze di runtime non condividono assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="03228-148">In addition, the two runtime instances don't share managed assemblies.</span></span> <span data-ttu-id="03228-149">Ciò significa che non è possibile condividere i tipi .NET effettivi tra i due runtime, ma tutte le interazioni devono essere limitate ai contratti di interfaccia COM esposti.</span><span class="sxs-lookup"><span data-stu-id="03228-149">This means that it isn't possible to share actual .NET types across the two runtimes and instead all interactions must be restricted to the exposed COM interface contracts.</span></span>
