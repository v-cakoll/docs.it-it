---
title: Opzioni di configurazione in fase di esecuzioneRun-time config options
description: Informazioni su come configurare le applicazioni .NET Core usando le impostazioni di configurazione di runtime.
ms.date: 01/21/2020
ms.openlocfilehash: ddf68c30e620a06856f65e71bd050e1b77618f20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79399161"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="cb86b-103">Impostazioni di configurazione di runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb86b-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="cb86b-104">.NET Core supporta l'utilizzo di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cb86b-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="cb86b-105">La configurazione in fase di esecuzione è un'opzione interessante se:Run-time configuration is an attractive option if:</span><span class="sxs-lookup"><span data-stu-id="cb86b-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="cb86b-106">Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="cb86b-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="cb86b-107">Più istanze dell'applicazione vengono eseguite contemporaneamente su un singolo sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="cb86b-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="cb86b-108">Questa documentazione è un work in progress.</span><span class="sxs-lookup"><span data-stu-id="cb86b-108">This documentation is a work in progress.</span></span> <span data-ttu-id="cb86b-109">Se si nota che le informazioni qui presentate sono incomplete o inesatte, [aprire un problema](https://github.com/dotnet/docs/issues) per comunicarcelo oppure [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="cb86b-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="cb86b-110">Per informazioni sull'invio di richieste pull per il repository dotnet/docs, vedere la [guida del collaboratore](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="cb86b-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="cb86b-111">.NET Core fornisce i meccanismi seguenti per la configurazione del comportamento dell'applicazione in fase di esecuzione:NET Core provides the following mechanisms for configuring run-time application behavior:</span><span class="sxs-lookup"><span data-stu-id="cb86b-111">.NET Core provides the following mechanisms for configuring run-time application behavior:</span></span>

- <span data-ttu-id="cb86b-112">Il [file runtimeconfig.json](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="cb86b-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="cb86b-113">Proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="cb86b-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="cb86b-114">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="cb86b-114">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="cb86b-115">Alcuni valori di configurazione possono anche <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> essere impostati a livello di codice chiamando il metodo .</span><span class="sxs-lookup"><span data-stu-id="cb86b-115">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="cb86b-116">Gli articoli di questa sezione della documentazione sono organizzati per categoria, ad esempio [debug](debugging-profiling.md) ed [operazione di Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="cb86b-116">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="cb86b-117">Se applicabile, vengono visualizzate le opzioni di configurazione per i file *runtimeconfig.json,* le proprietà MSBuild, le variabili di ambiente e, per i riferimenti incrociati, i file *app.config* per i progetti .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb86b-117">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="cb86b-118">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="cb86b-118">runtimeconfig.json</span></span>

<span data-ttu-id="cb86b-119">Quando un progetto viene [compilato](../tools/dotnet-build.md), nella directory di output viene generato un file *[appname].runtimeconfig.json* .</span><span class="sxs-lookup"><span data-stu-id="cb86b-119">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="cb86b-120">Se un file *runtimeconfig.template.json* è presente nella stessa cartella del file di progetto, tutte le opzioni di configurazione in esso contenute vengono unite nel file *[appname].runtimeconfig.json.*</span><span class="sxs-lookup"><span data-stu-id="cb86b-120">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are merged into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="cb86b-121">Se si sta compilando l'app manualmente, inserire le opzioni di configurazione nel file *runtimeconfig.template.json.*</span><span class="sxs-lookup"><span data-stu-id="cb86b-121">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="cb86b-122">Se stai solo eseguendo l'app, inseriscile direttamente nel file *[appname].runtimeconfig.json.*</span><span class="sxs-lookup"><span data-stu-id="cb86b-122">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="cb86b-123">Il file *[appname].runtimeconfig.json* verrà sovrascritto nelle compilazioni successive.</span><span class="sxs-lookup"><span data-stu-id="cb86b-123">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="cb86b-124">Specificare le opzioni di configurazione in fase di esecuzione nella sezione **configProperties** dei file *runtimeconfig.json.*</span><span class="sxs-lookup"><span data-stu-id="cb86b-124">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="cb86b-125">Questa sezione ha il modulo:</span><span class="sxs-lookup"><span data-stu-id="cb86b-125">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="cb86b-126">Esempio [appname].runtimeconfig.json file</span><span class="sxs-lookup"><span data-stu-id="cb86b-126">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="cb86b-127">Se si inseriscono le opzioni nel file JSON `runtimeOptions` di output, annidarle sotto la proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb86b-127">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

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

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="cb86b-128">Esempio di file runtimeconfig.template.jsonExample runtimeconfig.template.json file</span><span class="sxs-lookup"><span data-stu-id="cb86b-128">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="cb86b-129">Se si inseriscono le opzioni nel file JSON `runtimeOptions` del modello, omettere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb86b-129">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="cb86b-130">proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="cb86b-130">MSBuild properties</span></span>

<span data-ttu-id="cb86b-131">Alcune opzioni di configurazione in fase di esecuzione possono essere impostate utilizzando le proprietà MSBuild nel file *con estensione csproj* o *vbproj* dei progetti .NET Core in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="cb86b-131">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="cb86b-132">Le proprietà MSBuild hanno la precedenza sulle opzioni impostate nel file *runtimeconfig.template.json.*</span><span class="sxs-lookup"><span data-stu-id="cb86b-132">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="cb86b-133">Sovrascrivono inoltre le opzioni impostate nel file *[appname].runtimeconfig.json* in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cb86b-133">They also overwrite any options you set in the *[appname].runtimeconfig.json* file at build time.</span></span>

<span data-ttu-id="cb86b-134">Di seguito è riportato un file di progetto di tipo SDK di esempio con proprietà MSBuild per la configurazione del comportamento in fase di esecuzione:Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span><span class="sxs-lookup"><span data-stu-id="cb86b-134">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

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

<span data-ttu-id="cb86b-135">Le proprietà MSBuild per la configurazione del comportamento in fase di esecuzione sono indicate nei singoli articoli per ogni area, ad esempio [Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="cb86b-135">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span>

## <a name="environment-variables"></a><span data-ttu-id="cb86b-136">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="cb86b-136">Environment variables</span></span>

<span data-ttu-id="cb86b-137">Le variabili di ambiente possono essere utilizzate per fornire alcune informazioni di configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cb86b-137">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="cb86b-138">Le manopole di configurazione specificate come variabili di ambiente hanno in genere il prefisso **COMPlus_**.</span><span class="sxs-lookup"><span data-stu-id="cb86b-138">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="cb86b-139">È possibile definire le variabili di ambiente dal Pannello di controllo <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> di Windows, dalla riga di comando o a livello di codice chiamando il metodo su entrambi i sistemi basati su Windows e Unix.</span><span class="sxs-lookup"><span data-stu-id="cb86b-139">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="cb86b-140">Negli esempi seguenti viene illustrato come impostare una variabile di ambiente nella riga di comando:The following examples show how to set an environment variable at the command line:</span><span class="sxs-lookup"><span data-stu-id="cb86b-140">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
