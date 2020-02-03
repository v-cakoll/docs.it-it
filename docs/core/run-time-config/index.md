---
title: Opzioni di configurazione della fase di esecuzione
description: Informazioni su come configurare le applicazioni .NET Core usando le impostazioni di configurazione in fase di esecuzione.
ms.date: 01/21/2020
ms.openlocfilehash: ddf68c30e620a06856f65e71bd050e1b77618f20
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733444"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="ea859-103">Impostazioni di configurazione della fase di esecuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="ea859-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="ea859-104">.NET Core supporta l'uso di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ea859-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="ea859-105">La configurazione in fase di esecuzione è un'opzione interessante se:</span><span class="sxs-lookup"><span data-stu-id="ea859-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="ea859-106">Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="ea859-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="ea859-107">Più istanze dell'applicazione vengono eseguite contemporaneamente in un unico sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="ea859-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="ea859-108">Questa documentazione è un lavoro in corso.</span><span class="sxs-lookup"><span data-stu-id="ea859-108">This documentation is a work in progress.</span></span> <span data-ttu-id="ea859-109">Se si nota che le informazioni presentate in questo documento sono incomplete o non accurate, è possibile [aprire un problema](https://github.com/dotnet/docs/issues) per segnalarlo o [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="ea859-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="ea859-110">Per informazioni sull'invio di richieste pull per il repository DotNet/docs, vedere la guida per i [collaboratori](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="ea859-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="ea859-111">.NET Core fornisce i meccanismi seguenti per la configurazione del comportamento dell'applicazione in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="ea859-111">.NET Core provides the following mechanisms for configuring run-time application behavior:</span></span>

- <span data-ttu-id="ea859-112">Il [file runtimeconfig. JSON](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="ea859-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="ea859-113">Proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="ea859-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="ea859-114">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="ea859-114">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="ea859-115">Alcuni valori di configurazione possono essere impostati anche a livello di codice chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea859-115">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="ea859-116">Gli articoli di questa sezione della documentazione sono organizzati in base alla categoria, ad esempio [debug](debugging-profiling.md) e [Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="ea859-116">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="ea859-117">Se applicabile, vengono visualizzate le opzioni di configurazione per i file *runtimeconfig. JSON* , le proprietà MSBuild, le variabili di ambiente e, per i file *app. config* di riferimento incrociato per i progetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea859-117">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="ea859-118">runtimeconfig. JSON</span><span class="sxs-lookup"><span data-stu-id="ea859-118">runtimeconfig.json</span></span>

<span data-ttu-id="ea859-119">Quando viene [compilato](../tools/dotnet-build.md)un progetto, nella directory di output viene generato un file *[AppName]. runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="ea859-119">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="ea859-120">Se un file *runtimeconfig. template. JSON* è presente nella stessa cartella del file di progetto, tutte le opzioni di configurazione in esso contenute vengono unite nel file *[AppName]. runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="ea859-120">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are merged into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="ea859-121">Se l'app viene compilata manualmente, inserire le opzioni di configurazione nel file *runtimeconfig. template. JSON* .</span><span class="sxs-lookup"><span data-stu-id="ea859-121">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="ea859-122">Se si sta eseguendo semplicemente l'app, inserirle direttamente nel file *[AppName]. runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="ea859-122">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="ea859-123">Il file *[AppName]. runtimeconfig. JSON* viene sovrascritto nelle compilazioni successive.</span><span class="sxs-lookup"><span data-stu-id="ea859-123">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="ea859-124">Specificare le opzioni di configurazione in fase di esecuzione nella sezione **configProperties** dei file *runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="ea859-124">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="ea859-125">Questa sezione presenta il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="ea859-125">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="ea859-126">Esempio [AppName]. runtimeconfig. JSON</span><span class="sxs-lookup"><span data-stu-id="ea859-126">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="ea859-127">Se si inseriscono le opzioni nel file JSON di output, nidificarle sotto la proprietà `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="ea859-127">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="ea859-128">Esempio di file runtimeconfig. template. JSON</span><span class="sxs-lookup"><span data-stu-id="ea859-128">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="ea859-129">Se vengono posizionate le opzioni nel file JSON del modello, omettere la proprietà `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="ea859-129">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="ea859-130">proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="ea859-130">MSBuild properties</span></span>

<span data-ttu-id="ea859-131">Alcune opzioni di configurazione in fase di esecuzione possono essere impostate usando le proprietà di MSBuild nel file con *estensione csproj* o *VBPROJ* dei progetti .NET Core in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="ea859-131">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="ea859-132">Le proprietà di MSBuild hanno la precedenza sulle opzioni impostate nel file *runtimeconfig. template. JSON* .</span><span class="sxs-lookup"><span data-stu-id="ea859-132">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="ea859-133">Sovrascrivono anche le opzioni impostate nel file *[AppName]. runtimeconfig. JSON* in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ea859-133">They also overwrite any options you set in the *[appname].runtimeconfig.json* file at build time.</span></span>

<span data-ttu-id="ea859-134">Di seguito è riportato un esempio di file di progetto in stile SDK con proprietà MSBuild per la configurazione del comportamento in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="ea859-134">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="ea859-135">Le proprietà di MSBuild per la configurazione del comportamento in fase di esecuzione sono indicate nei singoli articoli per ogni area, ad esempio [Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="ea859-135">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span>

## <a name="environment-variables"></a><span data-ttu-id="ea859-136">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="ea859-136">Environment variables</span></span>

<span data-ttu-id="ea859-137">Le variabili di ambiente possono essere usate per fornire alcune informazioni di configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ea859-137">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="ea859-138">Le manopole di configurazione specificate come variabili di ambiente in genere hanno il prefisso **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="ea859-138">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="ea859-139">È possibile definire le variabili di ambiente dal pannello di controllo di Windows, dalla riga di comando o a livello di codice chiamando il metodo <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> nei sistemi basati su Windows e UNIX.</span><span class="sxs-lookup"><span data-stu-id="ea859-139">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="ea859-140">Gli esempi seguenti illustrano come impostare una variabile di ambiente dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="ea859-140">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
