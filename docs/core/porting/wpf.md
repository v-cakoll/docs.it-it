---
title: Convertire un'app WPF in .NET Core 3.0
description: Illustra come convertire un'applicazione Windows Presentation Foundation di NET Framework in .NET Core 3.0 per Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 29ea308ee5147cfb18df312887e933615e349803
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2019
ms.locfileid: "58677551"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a><span data-ttu-id="4a2a4-103">Procedura: Convertire un'app desktop WPF in .NET Core</span><span class="sxs-lookup"><span data-stu-id="4a2a4-103">How to: Port a WPF desktop app to .NET Core</span></span>

<span data-ttu-id="4a2a4-104">Questo articolo descrive come convertire l'app desktop basata su Windows Presentation Foundation (WPF) da .NET Framework a .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-104">This article describes how to port your Windows Presentation Foundation-based (WPF) desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="4a2a4-105">.NET Core SDK 3.0 include supporto per applicazioni WPF.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-105">The .NET Core 3.0 SDK includes support for WPF applications.</span></span> <span data-ttu-id="4a2a4-106">WPF è comunque un framework solo per Windows e supporta l'esecuzione solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-106">WPF is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="4a2a4-107">Questo esempio usa l'interfaccia della riga di comando di .NET Core SDK per creare e gestire il progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="4a2a4-108">In questo articolo vengono usati vari nomi per identificare i tipi di file usati per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="4a2a4-109">Durante la migrazione del progetto personale i file verranno denominati in modo diverso, pertanto abbinarli mentalmente a quelli elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="4a2a4-110">File</span><span class="sxs-lookup"><span data-stu-id="4a2a4-110">File</span></span> | <span data-ttu-id="4a2a4-111">Description</span><span class="sxs-lookup"><span data-stu-id="4a2a4-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="4a2a4-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-112">**MyApps.sln**</span></span> | <span data-ttu-id="4a2a4-113">Nome del file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-113">The name of the solution file.</span></span> |
| <span data-ttu-id="4a2a4-114">**MyWPF.csproj**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-114">**MyWPF.csproj**</span></span> | <span data-ttu-id="4a2a4-115">Nome del progetto WPF di .NET Framework da convertire.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-115">The name of the .NET Framework WPF project to port.</span></span> |
| <span data-ttu-id="4a2a4-116">**MyWPFCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-116">**MyWPFCore.csproj**</span></span> | <span data-ttu-id="4a2a4-117">Nome del nuovo progetto .NET Core creato.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="4a2a4-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="4a2a4-119">App WPF di .NET Core eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-119">The .NET Core WPF app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="4a2a4-120">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4a2a4-120">Prerequisites</span></span>

- <span data-ttu-id="4a2a4-121">[Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=wpf+core) per tutte le operazioni di progettazione che si vogliono eseguire.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-121">[Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=wpf+core) for any designer work you want to do.</span></span>

  <span data-ttu-id="4a2a4-122">Installare i carichi di lavoro di Visual Studio seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="4a2a4-123">Sviluppo per desktop .NET</span><span class="sxs-lookup"><span data-stu-id="4a2a4-123">.NET desktop development</span></span>
  - <span data-ttu-id="4a2a4-124">Sviluppo multipiattaforma .NET Core</span><span class="sxs-lookup"><span data-stu-id="4a2a4-124">.NET cross-platform development</span></span>

- <span data-ttu-id="4a2a4-125">Un progetto WPF in uso in una soluzione che viene compilata ed eseguita senza problemi.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-125">A working WPF project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="4a2a4-126">Il progetto deve essere codificato in C#.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-126">Your project must be coded in C#.</span></span> 
- <span data-ttu-id="4a2a4-127">Installare l'anteprima più recente di [.NET Core 3.0](https://aka.ms/netcore3download).</span><span class="sxs-lookup"><span data-stu-id="4a2a4-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>


>[!NOTE]
><span data-ttu-id="4a2a4-128">**Visual Studio 2017** non supporta progetti .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="4a2a4-129">**Visual Studio 2019 Preview/RC** supporta i progetti .NET Core 3.0, ma non supporta ancora la finestra di progettazione grafica per i progetti WPF di .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-129">**Visual Studio 2019 Preview/RC** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 WPF projects.</span></span> <span data-ttu-id="4a2a4-130">Per usare la finestra di progettazione grafica, è necessario avere un progetto WPF di .NET nella soluzione che condivide i file con il progetto .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-130">To use the visual designer, you must have a .NET WPF project in your solution that shares its files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="4a2a4-131">Consider</span><span class="sxs-lookup"><span data-stu-id="4a2a4-131">Consider</span></span>

<span data-ttu-id="4a2a4-132">Per la conversione di un'applicazione WPF di .NET Framework, esistono alcuni aspetti da considerare.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-132">When porting a .NET Framework WPF application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="4a2a4-133">Controllare che l'applicazione sia un buon candidato per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="4a2a4-134">Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per determinare se sarà possibile eseguire la migrazione del progetto a .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="4a2a4-135">Se il progetto presenta problemi con .NET Core 3.0, l'analizzatore consente di identificarli.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="4a2a4-136">Si usa una versione diversa di WPF.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-136">You're using a different version of WPF.</span></span>

    <span data-ttu-id="4a2a4-137">In concomitanza con il rilascio di .NET Core 3.0 Preview 1, è stato reso disponibile WPF come open source su GitHub.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-137">When .NET Core 3.0 Preview 1 was released, WPF went open-source on GitHub.</span></span> <span data-ttu-id="4a2a4-138">Il codice per WPF di .NET Core è un fork della base di codice di WPF di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-138">The code for .NET Core WPF is a fork of the .NET Framework WPF code base.</span></span> <span data-ttu-id="4a2a4-139">È possibile che esistano alcune differenze che non consentono la conversione dell'app.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="4a2a4-140">[Windows Compatibility Pack][compat-pack] può essere utile per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="4a2a4-141">Alcune API che sono disponibili in .NET Framework non sono disponibili in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="4a2a4-142">[Windows Compatibility Pack][compat-pack] aggiunge molte di queste API e può essere utile per rendere l'app WPF compatibile con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your WPF app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="4a2a4-143">Aggiornare i pacchetti NuGet usati dal progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="4a2a4-144">È sempre consigliabile usare le versioni più recenti dei pacchetti NuGet prima di qualsiasi migrazione.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="4a2a4-145">Se l'applicazione fa riferimento a pacchetti NuGet, aggiornarli alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="4a2a4-146">Verificare che l'applicazione venga compilata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="4a2a4-147">Dopo l'aggiornamento, se sono presenti errori di pacchetto, effettuare il downgrade del pacchetto alla versione più recente che non causa problemi al codice.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="4a2a4-148">Visual Studio 2019 Preview/RC non supporta ancora WPF Designer per .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4a2a4-148">Visual Studio 2019 Preview/RC doesn't yet support the WPF Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="4a2a4-149">Attualmente è necessario mantenere il file di progetto WPF di .NET Framework esistente se si vuole usare WPF Designer da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-149">Currently, you need to keep your existing .NET Framework WPF project file if you want to use the WPF Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="4a2a4-150">Creare un nuovo progetto SDK</span><span class="sxs-lookup"><span data-stu-id="4a2a4-150">Create a new SDK project</span></span>

<span data-ttu-id="4a2a4-151">Il nuovo progetto .NET Core 3.0 creato deve essere in una directory diversa dal progetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="4a2a4-152">Se si trovano entrambi nella stessa directory, è possibile che si verifichino conflitti con i file generati nella directory **obj**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="4a2a4-153">In questo esempio si creerà una directory denominata **MyWPFAppCore** nella directory **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-153">In this example, you'll create a directory named **MyWPFAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

<span data-ttu-id="4a2a4-154">Quindi sarà necessario creare il progetto **MyWPFCore.csproj** nella directory **MyWPFAppCore**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-154">Next, you need to create the **MyWPFCore.csproj** project in the **MyWPFAppCore** directory.</span></span> <span data-ttu-id="4a2a4-155">È possibile creare questo file manualmente usando l'editor di testo preferito.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="4a2a4-156">Incollare il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="4a2a4-157">Se non si vuole creare manualmente il file di progetto, è possibile usare Visual Studio o .NET Core SDK per generare il progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="4a2a4-158">Tuttavia, è necessario eliminare tutti gli altri file generati dal modello di progetto, ad eccezione del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="4a2a4-159">Per usare l'SDK, eseguire il comando seguente dalla directory **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

<span data-ttu-id="4a2a4-160">Dopo aver creato **MyWPFCore.csproj**, la struttura della directory dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-160">After you create the **MyWPFCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

<span data-ttu-id="4a2a4-161">Il progetto **MyFormsCore.csproj** sarà aggiunto a **MyApps.sln** con Visual Studio o con l'interfaccia della riga di comando di .NET Core dalla directory **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-161">You'll want to add the **MyWPFCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="4a2a4-162">Correggere la generazione delle informazioni sull'assembly</span><span class="sxs-lookup"><span data-stu-id="4a2a4-162">Fix assembly info generation</span></span>

<span data-ttu-id="4a2a4-163">I progetti Windows Presentation Foundation che sono stati creati con .NET Framework includono un file `AssemblyInfo.cs` che contiene gli attributi dell'assembly, ad esempio la versione dell'assembly da generare.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-163">Windows Presentation Foundation projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="4a2a4-164">I progetti in stile SDK generano automaticamente queste informazioni in base al file di progetto SDK.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="4a2a4-165">La presenza di entrambi i tipi di "informazioni sull'assembly" crea un conflitto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="4a2a4-166">Per risolvere questo problema, disabilitare la generazione automatica, che impone l'uso del file `AssemblyInfo.cs` esistente nel progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="4a2a4-167">Sono disponibili tre impostazioni da aggiungere al nodo `<PropertyGroup>` principale.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- <span data-ttu-id="4a2a4-168">**GenerateAssemblyInfo**\\</span><span class="sxs-lookup"><span data-stu-id="4a2a4-168">**GenerateAssemblyInfo**\\</span></span>
<span data-ttu-id="4a2a4-169">Quando si imposta questa proprietà su `false`, non verranno generati gli attributi dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="4a2a4-170">Ciò consente di evitare il conflitto con il file `AssemblyInfo.cs` esistente dal progetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="4a2a4-171">**AssemblyName**\\</span><span class="sxs-lookup"><span data-stu-id="4a2a4-171">**AssemblyName**\\</span></span>
<span data-ttu-id="4a2a4-172">Il valore di questa proprietà è il file binario di output creato durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="4a2a4-173">Non è necessario aggiungere un'estensione al nome.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="4a2a4-174">Ad esempio, `MyCoreApp` produce `MyCoreApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="4a2a4-175">**RootNamespace**\\</span><span class="sxs-lookup"><span data-stu-id="4a2a4-175">**RootNamespace**\\</span></span>
<span data-ttu-id="4a2a4-176">Spazio dei nomi predefinito usato dal progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-176">The default namespace used by your project.</span></span> <span data-ttu-id="4a2a4-177">Deve corrispondere allo spazio dei nomi predefinito del progetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="4a2a4-178">Aggiungere questi tre elementi al nodo `<PropertyGroup>` nel file `MyWPFCore.csproj`:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-178">Add these three elements to the `<PropertyGroup>` node in the `MyWPFCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="4a2a4-179">Aggiungere codice sorgente</span><span class="sxs-lookup"><span data-stu-id="4a2a4-179">Add source code</span></span>
<span data-ttu-id="4a2a4-180">Il progetto **MyWPFCore.csproj** per il momento non compila il codice.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-180">Right now, the **MyWPFCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="4a2a4-181">Per impostazione predefinita, i progetti .NET Core includono automaticamente tutto il codice sorgente nella directory corrente e in eventuali directory figlio.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="4a2a4-182">È necessario configurare il progetto per includere il codice dal progetto .NET Framework usando un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="4a2a4-183">Se il progetto .NET Framework usava file **con estensione resx** per le icone e le risorse delle finestre e dei controlli, sarà necessario includere anche questi.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-183">If your .NET Framework project used **.resx** files for icons and resources for your windows and controls, you'll need to include those too.</span></span> 

<span data-ttu-id="4a2a4-184">Il primo nodo `<ItemGroup>` da aggiungere al progetto include il file **App.xaml** che rappresenta la configurazione di avvio e le risorse usate dall'app.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-184">The first `<ItemGroup>` node you need to add to your project includes the **App.xaml** file that represents the startup config and resources your app uses.</span></span> <span data-ttu-id="4a2a4-185">Il file **App.xaml** include anche un file **App.xaml.cs** di accompagnamento, che sarà tuttavia incluso automaticamente in un elemento `<ItemGroup>` diverso.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-185">The **App.xaml** file also has an accompanying **App.xaml.cs** file, but it will be automatically included in a different `<ItemGroup>`.</span></span>

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

<span data-ttu-id="4a2a4-186">A questo punto aggiungere il nodo `<ItemGroup>` seguente al progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-186">Next, add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="4a2a4-187">Ogni istruzione include un criterio GLOB per i file che include le directory figlio.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-187">Each statement includes a file glob pattern that includes child directories.</span></span> <span data-ttu-id="4a2a4-188">Include il codice sorgente per il progetto, tutti i file di impostazioni e tutte le risorse.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-188">It includes the source code for your project, any settings files, and any resources.</span></span> <span data-ttu-id="4a2a4-189">La directory **obj** è esplicitamente esclusa.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-189">The **obj** directory is explicitly excluded.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="4a2a4-190">Quindi includere un altro nodo `<ItemGroup>` che contiene una voce `<Page>` per ogni file **xaml** nel progetto, ad eccezione del file **App.xaml**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-190">Next, include another `<ItemGroup>` node that contains a `<Page>` entry for every **xaml** file in your project except the **App.xaml** file.</span></span> <span data-ttu-id="4a2a4-191">Contengono tutte le finestre, le pagine e le risorse nel formato **xaml**.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-191">These contain all of the windows, pages, and resources that are in **xaml** format.</span></span> <span data-ttu-id="4a2a4-192">Qui non è possibile usare un criterio GLOB. È necessario aggiungere una voce per ogni file e indicare l'elemento `<Generator>` usato.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-192">You cannot use a glob pattern here and must add an entry for every file and indicate the `<Generator>` used.</span></span>

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a><span data-ttu-id="4a2a4-193">Aggiungere pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="4a2a4-193">Add NuGet packages</span></span>

<span data-ttu-id="4a2a4-194">Aggiungere al progetto .NET Core ogni pacchetto NuGet a cui fa riferimento il progetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-194">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="4a2a4-195">È molto probabile che l'app WPF di .NET Framework includa un file **packages.config** che contiene un elenco di tutti i pacchetti NuGet a cui fa riferimento il progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-195">Most likely your .NET Framework WPF app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="4a2a4-196">È possibile esaminare questo elenco per determinare quali pacchetti NuGet aggiungere al progetto .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-196">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="4a2a4-197">Ad esempio, se il progetto .NET Framework fa riferimento al pacchetto NuGet `MahApps.Metro`, aggiungerlo al progetto usando Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-197">For example, if the .NET Framework project references the `MahApps.Metro` NuGet package, add it to the project with Visual Studio.</span></span> <span data-ttu-id="4a2a4-198">È anche possibile aggiungere un riferimento al pacchetto con l'interfaccia della riga di comando di .NET Core dalla directory **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-198">You can also add the package reference with the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

<span data-ttu-id="4a2a4-199">Il comando precedente consente di aggiungere il riferimento NuGet seguente al progetto **MyWPFCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-199">The previous command would add the following NuGet reference to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="4a2a4-200">Problemi di compilazione</span><span class="sxs-lookup"><span data-stu-id="4a2a4-200">Problems compiling</span></span>

<span data-ttu-id="4a2a4-201">Se si riscontrano problemi durante la compilazione dei progetti, è possibile che siano in uso alcune API solo per Windows disponibili in .NET Framework, ma non in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-201">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="4a2a4-202">È possibile provare ad aggiungere il pacchetto NuGet [Windows Compatibility Pack][compat-pack] al progetto.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-202">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="4a2a4-203">Questo pacchetto può essere eseguito solo in Windows e aggiunge circa 20.000 API Windows ai progetti .NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-203">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="4a2a4-204">Il comando precedente aggiunge il codice seguente al progetto **MyWPFCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="4a2a4-204">The previous command adds the following to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a><span data-ttu-id="4a2a4-205">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="4a2a4-205">WPF Designer</span></span>

<span data-ttu-id="4a2a4-206">Come descritto in dettaglio in questo articolo, Visual Studio 2019 Preview/RC supporta solo WPF Designer nei progetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-206">As detailed in this article, Visual Studio 2019 Preview/RC only supports the WPF Designer in .NET Framework projects.</span></span> <span data-ttu-id="4a2a4-207">È possibile creare un progetto .NET Core affiancato per testare il progetto .NET Core mentre si usa progetto .NET Framework per la progettazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-207">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="4a2a4-208">Il file di soluzione include sia i progetti .NET Framework che .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-208">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="4a2a4-209">Aggiungere e progettare i moduli e i controlli nel progetto .NET Framework e, in base ai criteri GLOB per i file aggiunti ai progetti .NET Core, qualsiasi file nuovo o modificato verrà incluso automaticamente nei progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-209">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="4a2a4-210">Quando Visual Studio 2019 supporterà WPF Designer, sarà possibile copiare e incollare il contenuto del file di progetto .NET Core nel file di progetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-210">Once Visual Studio 2019 supports the WPF Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="4a2a4-211">Eliminare quindi i criteri GLOB per i file aggiunti con gli elementi `<Source>` e `<EmbeddedResource>`.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-211">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="4a2a4-212">Correggere i percorsi per qualsiasi riferimento del progetto usato dall'app.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-212">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="4a2a4-213">In questo modo il progetto .NET Framework viene effettivamente aggiornato a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-213">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="4a2a4-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4a2a4-214">Next steps</span></span>

* <span data-ttu-id="4a2a4-215">Vedere altre informazioni su [Windows Compatibility Pack][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="4a2a4-215">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
* <span data-ttu-id="4a2a4-216">Guardare un [video sulla conversione](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) del progetto WPF di .NET Framework in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a2a4-216">Watch a [video on porting](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) your .NET Framework WPF project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
