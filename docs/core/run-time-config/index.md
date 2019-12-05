---
title: Configurazione della fase di esecuzione
description: Informazioni su come configurare le applicazioni .NET Core usando le impostazioni di configurazione in fase di esecuzione.
ms.date: 11/13/2019
ms.openlocfilehash: 2665026347e94d26026821beb2bfcf8441f755f6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801924"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="8db7d-103">Impostazioni di configurazione della fase di esecuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="8db7d-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="8db7d-104">.NET Core supporta l'uso di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8db7d-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="8db7d-105">La configurazione in fase di esecuzione è un'opzione interessante se:</span><span class="sxs-lookup"><span data-stu-id="8db7d-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="8db7d-106">Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8db7d-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="8db7d-107">Più istanze dell'applicazione vengono eseguite contemporaneamente in un unico sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="8db7d-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="8db7d-108">Questa documentazione è un lavoro in corso.</span><span class="sxs-lookup"><span data-stu-id="8db7d-108">This documentation is a work in progress.</span></span> <span data-ttu-id="8db7d-109">Se si nota che le informazioni presentate in questo documento sono incomplete o non accurate, è possibile [aprire un problema](https://github.com/dotnet/docs/issues) per segnalarlo o [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="8db7d-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="8db7d-110">Per informazioni sull'invio di richieste pull per il repository DotNet/docs, vedere la guida per i [collaboratori](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="8db7d-110">For information on submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="8db7d-111">.NET Core fornisce i meccanismi seguenti per la configurazione delle applicazioni in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="8db7d-111">.NET Core provides the following mechanisms for configuring applications at run time:</span></span>

- <span data-ttu-id="8db7d-112">Il [file runtimeconfig. JSON](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="8db7d-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="8db7d-113">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="8db7d-113">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="8db7d-114">Gli articoli di questa sezione della documentazione includono sono organizzati per categoria, ad esempio debug e Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8db7d-114">The articles in this section of the documentation include are organized by category, for example, debugging and garbage collection.</span></span> <span data-ttu-id="8db7d-115">Se applicabile, vengono visualizzate le opzioni di configurazione per *runtimeconfig. JSON* (solo .NET Core), *app. config* (solo .NET Framework) e le variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8db7d-115">Where applicable, configuration options are shown for *runtimeconfig.json* (.NET Core only), *app.config* (.NET Framework only), and environment variables.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="8db7d-116">runtimeconfig. JSON</span><span class="sxs-lookup"><span data-stu-id="8db7d-116">runtimeconfig.json</span></span>

<span data-ttu-id="8db7d-117">Specificare le opzioni di configurazione in fase di esecuzione nella sezione **configProperties** del file *runtimeconfig. JSON* dell'app.</span><span class="sxs-lookup"><span data-stu-id="8db7d-117">Specify run-time configuration options in the **configProperties** section of the app's *runtimeconfig.json* file.</span></span> <span data-ttu-id="8db7d-118">Questa sezione presenta il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="8db7d-118">This section has the form:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

<span data-ttu-id="8db7d-119">Di seguito è riportato un esempio di file:</span><span class="sxs-lookup"><span data-stu-id="8db7d-119">Here is an example file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

<span data-ttu-id="8db7d-120">Il file *runtimeconfig. JSON* viene creato automaticamente nella directory di compilazione tramite il comando [DotNet Build](../tools/dotnet-build.md) .</span><span class="sxs-lookup"><span data-stu-id="8db7d-120">The *runtimeconfig.json* file is automatically created in the build directory by the [dotnet build](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="8db7d-121">Viene creato anche quando si seleziona l'opzione di menu **Compila** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8db7d-121">It's also created when you select the **Build** menu option in Visual Studio.</span></span> <span data-ttu-id="8db7d-122">È quindi possibile modificare il file dopo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="8db7d-122">You can then edit the file once it's created.</span></span>

<span data-ttu-id="8db7d-123">Alcuni valori di configurazione possono essere impostati anche a livello di codice chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8db7d-123">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="8db7d-124">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="8db7d-124">Environment variables</span></span>

<span data-ttu-id="8db7d-125">Le variabili di ambiente possono essere usate per fornire alcune informazioni di configurazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8db7d-125">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="8db7d-126">Le manopole di configurazione specificate come variabili di ambiente in genere hanno il prefisso **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="8db7d-126">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="8db7d-127">È possibile definire le variabili di ambiente dal pannello di controllo di Windows, dalla riga di comando o a livello di codice chiamando il metodo <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> nei sistemi basati su Windows e UNIX.</span><span class="sxs-lookup"><span data-stu-id="8db7d-127">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="8db7d-128">Gli esempi seguenti illustrano come impostare una variabile di ambiente dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="8db7d-128">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
