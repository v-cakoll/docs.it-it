---
title: Opzioni di configurazione della fase di esecuzione
description: Informazioni su come configurare le applicazioni .NET Core usando le impostazioni di configurazione in fase di esecuzione.
ms.date: 01/21/2020
ms.openlocfilehash: 68690689fd4f936e3af76ab647f0b58d8ec6ca27
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761954"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="45263-103">Impostazioni di configurazione della fase di esecuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="45263-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="45263-104">.NET Core supporta l'uso di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45263-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="45263-105">La configurazione in fase di esecuzione è un'opzione interessante se:</span><span class="sxs-lookup"><span data-stu-id="45263-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="45263-106">Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="45263-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="45263-107">Più istanze dell'applicazione vengono eseguite contemporaneamente in un unico sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="45263-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="45263-108">Questa documentazione è un lavoro in corso.</span><span class="sxs-lookup"><span data-stu-id="45263-108">This documentation is a work in progress.</span></span> <span data-ttu-id="45263-109">Se si nota che le informazioni presentate in questo documento sono incomplete o non accurate, è possibile [aprire un problema](https://github.com/dotnet/docs/issues) per segnalarlo o [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="45263-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="45263-110">Per informazioni sull'invio di richieste pull per il repository DotNet/docs, vedere la guida per i [collaboratori](https://docs.microsoft.com/contribute/dotnet/dotnet-contribute).</span><span class="sxs-lookup"><span data-stu-id="45263-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://docs.microsoft.com/contribute/dotnet/dotnet-contribute).</span></span>

<span data-ttu-id="45263-111">.NET Core fornisce i meccanismi seguenti per configurare il comportamento dell'applicazione in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="45263-111">.NET Core provides the following mechanisms for configuring application behavior at run time:</span></span>

- <span data-ttu-id="45263-112">Il [file runtimeconfig. JSON](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="45263-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="45263-113">Proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="45263-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="45263-114">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="45263-114">Environment variables</span></span>](#environment-variables)

> [!TIP]
> <span data-ttu-id="45263-115">La configurazione di un'opzione della fase di esecuzione tramite una variabile di ambiente applica l'impostazione a tutte le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="45263-115">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="45263-116">La configurazione di un'opzione in fase di esecuzione nel file *runtimeconfig. JSON* o di progetto applica l'impostazione solo a tale applicazione.</span><span class="sxs-lookup"><span data-stu-id="45263-116">Configuring a run-time option in the *runtimeconfig.json* or project file applies the setting to that application only.</span></span>

<span data-ttu-id="45263-117">Alcuni valori di configurazione possono essere impostati anche a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="45263-117">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="45263-118">Gli articoli di questa sezione della documentazione sono organizzati in base alla categoria, ad esempio [debug](debugging-profiling.md) e [Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="45263-118">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="45263-119">Se applicabile, vengono visualizzate le opzioni di configurazione per i file *runtimeconfig. JSON* , le proprietà MSBuild, le variabili di ambiente e, per i file *app. config* di riferimento incrociato per i progetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45263-119">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="45263-120">runtimeconfig. JSON</span><span class="sxs-lookup"><span data-stu-id="45263-120">runtimeconfig.json</span></span>

<span data-ttu-id="45263-121">Quando viene [compilato](../tools/dotnet-build.md)un progetto, nella directory di output viene generato un file *[AppName]. runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="45263-121">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="45263-122">Se un file *runtimeconfig. template. JSON* è presente nella stessa cartella del file di progetto, tutte le opzioni di configurazione in esso contenute vengono unite nel file *[AppName]. runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="45263-122">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are merged into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="45263-123">Se l'app viene compilata manualmente, inserire le opzioni di configurazione nel file *runtimeconfig. template. JSON* .</span><span class="sxs-lookup"><span data-stu-id="45263-123">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="45263-124">Se si sta eseguendo semplicemente l'app, inserirle direttamente nel file *[AppName]. runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="45263-124">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="45263-125">Il file *[AppName]. runtimeconfig. JSON* viene sovrascritto nelle compilazioni successive.</span><span class="sxs-lookup"><span data-stu-id="45263-125">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="45263-126">Specificare le opzioni di configurazione in fase di esecuzione nella sezione **configProperties** dei file *runtimeconfig. JSON* .</span><span class="sxs-lookup"><span data-stu-id="45263-126">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="45263-127">Questa sezione presenta il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="45263-127">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="45263-128">Esempio [AppName]. runtimeconfig. JSON</span><span class="sxs-lookup"><span data-stu-id="45263-128">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="45263-129">Se si posizionano le opzioni nel file JSON di output, nidificarle nella `runtimeOptions` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="45263-129">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

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

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="45263-130">Esempio di file runtimeconfig. template. JSON</span><span class="sxs-lookup"><span data-stu-id="45263-130">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="45263-131">Se si stanno inserendo le opzioni nel file JSON del modello, omettere la `runtimeOptions` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="45263-131">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="45263-132">proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="45263-132">MSBuild properties</span></span>

<span data-ttu-id="45263-133">Alcune opzioni di configurazione in fase di esecuzione possono essere impostate usando le proprietà di MSBuild nel file con *estensione csproj* o *VBPROJ* dei progetti .NET Core in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="45263-133">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="45263-134">Le proprietà di MSBuild hanno la precedenza sulle opzioni impostate nel file *runtimeconfig. template. JSON* .</span><span class="sxs-lookup"><span data-stu-id="45263-134">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="45263-135">Sovrascrivono anche le opzioni impostate nel file *[AppName]. runtimeconfig. JSON* in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="45263-135">They also overwrite any options you set in the *[appname].runtimeconfig.json* file at build time.</span></span>

<span data-ttu-id="45263-136">Di seguito è riportato un esempio di file di progetto in stile SDK con proprietà MSBuild per la configurazione del comportamento in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="45263-136">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

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

<span data-ttu-id="45263-137">Le proprietà di MSBuild per la configurazione del comportamento in fase di esecuzione sono indicate nei singoli articoli per ogni area, ad esempio [Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="45263-137">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="45263-138">Sono inoltre elencate nella sezione relativa alla configurazione della fase di [esecuzione](../project-sdk/msbuild-props.md#run-time-configuration-properties) del riferimento alle proprietà di MSBuild per i progetti in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="45263-138">They are also listed in the [Run-time configuration](../project-sdk/msbuild-props.md#run-time-configuration-properties) section of the MSBuild properties reference for SDK-style projects.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="45263-139">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="45263-139">Environment variables</span></span>

<span data-ttu-id="45263-140">Le variabili di ambiente possono essere usate per fornire alcune informazioni di configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45263-140">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="45263-141">La configurazione di un'opzione della fase di esecuzione tramite una variabile di ambiente applica l'impostazione a tutte le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="45263-141">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="45263-142">Le manopole di configurazione specificate come variabili di ambiente in genere hanno il prefisso **COMPlus_**.</span><span class="sxs-lookup"><span data-stu-id="45263-142">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="45263-143">È possibile definire le variabili di ambiente dal pannello di controllo di Windows, dalla riga di comando o a livello di codice chiamando il <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> metodo in entrambi i sistemi basati su Windows e UNIX.</span><span class="sxs-lookup"><span data-stu-id="45263-143">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="45263-144">Gli esempi seguenti illustrano come impostare una variabile di ambiente dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="45263-144">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
