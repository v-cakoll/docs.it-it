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
# <a name="net-core-run-time-configuration-settings"></a>Impostazioni di configurazione di runtime di .NET Core

.NET Core supporta l'utilizzo di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione. La configurazione in fase di esecuzione è un'opzione interessante se:Run-time configuration is an attractive option if:

- Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di codice.

- Più istanze dell'applicazione vengono eseguite contemporaneamente su un singolo sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.

> [!NOTE]
> Questa documentazione è un work in progress. Se si nota che le informazioni qui presentate sono incomplete o inesatte, [aprire un problema](https://github.com/dotnet/docs/issues) per comunicarcelo oppure [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema. Per informazioni sull'invio di richieste pull per il repository dotnet/docs, vedere la [guida del collaboratore](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).

.NET Core fornisce i meccanismi seguenti per la configurazione del comportamento dell'applicazione in fase di esecuzione:NET Core provides the following mechanisms for configuring run-time application behavior:

- Il [file runtimeconfig.json](#runtimeconfigjson)

- [Proprietà di MSBuild](#msbuild-properties)

- [Variabili di ambiente](#environment-variables)

Alcuni valori di configurazione possono anche <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> essere impostati a livello di codice chiamando il metodo .

Gli articoli di questa sezione della documentazione sono organizzati per categoria, ad esempio [debug](debugging-profiling.md) ed [operazione di Garbage Collection](garbage-collector.md). Se applicabile, vengono visualizzate le opzioni di configurazione per i file *runtimeconfig.json,* le proprietà MSBuild, le variabili di ambiente e, per i riferimenti incrociati, i file *app.config* per i progetti .NET Framework.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

Quando un progetto viene [compilato](../tools/dotnet-build.md), nella directory di output viene generato un file *[appname].runtimeconfig.json* . Se un file *runtimeconfig.template.json* è presente nella stessa cartella del file di progetto, tutte le opzioni di configurazione in esso contenute vengono unite nel file *[appname].runtimeconfig.json.* Se si sta compilando l'app manualmente, inserire le opzioni di configurazione nel file *runtimeconfig.template.json.* Se stai solo eseguendo l'app, inseriscile direttamente nel file *[appname].runtimeconfig.json.*

> [!NOTE]
> Il file *[appname].runtimeconfig.json* verrà sovrascritto nelle compilazioni successive.

Specificare le opzioni di configurazione in fase di esecuzione nella sezione **configProperties** dei file *runtimeconfig.json.* Questa sezione ha il modulo:

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a>Esempio [appname].runtimeconfig.json file

Se si inseriscono le opzioni nel file JSON `runtimeOptions` di output, annidarle sotto la proprietà.

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

### <a name="example-runtimeconfigtemplatejson-file"></a>Esempio di file runtimeconfig.template.jsonExample runtimeconfig.template.json file

Se si inseriscono le opzioni nel file JSON `runtimeOptions` del modello, omettere la proprietà.

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a>proprietà di MSBuild

Alcune opzioni di configurazione in fase di esecuzione possono essere impostate utilizzando le proprietà MSBuild nel file *con estensione csproj* o *vbproj* dei progetti .NET Core in stile SDK. Le proprietà MSBuild hanno la precedenza sulle opzioni impostate nel file *runtimeconfig.template.json.* Sovrascrivono inoltre le opzioni impostate nel file *[appname].runtimeconfig.json* in fase di compilazione.

Di seguito è riportato un file di progetto di tipo SDK di esempio con proprietà MSBuild per la configurazione del comportamento in fase di esecuzione:Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:

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

Le proprietà MSBuild per la configurazione del comportamento in fase di esecuzione sono indicate nei singoli articoli per ogni area, ad esempio [Garbage Collection](garbage-collector.md).

## <a name="environment-variables"></a>Variabili di ambiente

Le variabili di ambiente possono essere utilizzate per fornire alcune informazioni di configurazione in fase di esecuzione. Le manopole di configurazione specificate come variabili di ambiente hanno in genere il prefisso **COMPlus_**.

È possibile definire le variabili di ambiente dal Pannello di controllo <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> di Windows, dalla riga di comando o a livello di codice chiamando il metodo su entrambi i sistemi basati su Windows e Unix.

Negli esempi seguenti viene illustrato come impostare una variabile di ambiente nella riga di comando:The following examples show how to set an environment variable at the command line:

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
