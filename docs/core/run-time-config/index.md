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
# <a name="net-core-run-time-configuration-settings"></a>Impostazioni di configurazione della fase di esecuzione di .NET Core

.NET Core supporta l'uso di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione. La configurazione in fase di esecuzione è un'opzione interessante se:

- Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di programmazione.

- Più istanze dell'applicazione vengono eseguite contemporaneamente in un unico sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.

> [!NOTE]
> Questa documentazione è un lavoro in corso. Se si nota che le informazioni presentate in questo documento sono incomplete o non accurate, è possibile [aprire un problema](https://github.com/dotnet/docs/issues) per segnalarlo o [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema. Per informazioni sull'invio di richieste pull per il repository DotNet/docs, vedere la guida per i [collaboratori](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).

.NET Core fornisce i meccanismi seguenti per la configurazione del comportamento dell'applicazione in fase di esecuzione:

- Il [file runtimeconfig. JSON](#runtimeconfigjson)

- [Proprietà di MSBuild](#msbuild-properties)

- [Variabili di ambiente](#environment-variables)

Alcuni valori di configurazione possono essere impostati anche a livello di codice chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

Gli articoli di questa sezione della documentazione sono organizzati in base alla categoria, ad esempio [debug](debugging-profiling.md) e [Garbage Collection](garbage-collector.md). Se applicabile, vengono visualizzate le opzioni di configurazione per i file *runtimeconfig. JSON* , le proprietà MSBuild, le variabili di ambiente e, per i file *app. config* di riferimento incrociato per i progetti .NET Framework.

## <a name="runtimeconfigjson"></a>runtimeconfig. JSON

Quando viene [compilato](../tools/dotnet-build.md)un progetto, nella directory di output viene generato un file *[AppName]. runtimeconfig. JSON* . Se un file *runtimeconfig. template. JSON* è presente nella stessa cartella del file di progetto, tutte le opzioni di configurazione in esso contenute vengono unite nel file *[AppName]. runtimeconfig. JSON* . Se l'app viene compilata manualmente, inserire le opzioni di configurazione nel file *runtimeconfig. template. JSON* . Se si sta eseguendo semplicemente l'app, inserirle direttamente nel file *[AppName]. runtimeconfig. JSON* .

> [!NOTE]
> Il file *[AppName]. runtimeconfig. JSON* viene sovrascritto nelle compilazioni successive.

Specificare le opzioni di configurazione in fase di esecuzione nella sezione **configProperties** dei file *runtimeconfig. JSON* . Questa sezione presenta il formato seguente:

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a>Esempio [AppName]. runtimeconfig. JSON

Se si inseriscono le opzioni nel file JSON di output, nidificarle sotto la proprietà `runtimeOptions`.

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

### <a name="example-runtimeconfigtemplatejson-file"></a>Esempio di file runtimeconfig. template. JSON

Se vengono posizionate le opzioni nel file JSON del modello, omettere la proprietà `runtimeOptions`.

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

Alcune opzioni di configurazione in fase di esecuzione possono essere impostate usando le proprietà di MSBuild nel file con *estensione csproj* o *VBPROJ* dei progetti .NET Core in stile SDK. Le proprietà di MSBuild hanno la precedenza sulle opzioni impostate nel file *runtimeconfig. template. JSON* . Sovrascrivono anche le opzioni impostate nel file *[AppName]. runtimeconfig. JSON* in fase di compilazione.

Di seguito è riportato un esempio di file di progetto in stile SDK con proprietà MSBuild per la configurazione del comportamento in fase di esecuzione:

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

Le proprietà di MSBuild per la configurazione del comportamento in fase di esecuzione sono indicate nei singoli articoli per ogni area, ad esempio [Garbage Collection](garbage-collector.md).

## <a name="environment-variables"></a>Variabili di ambiente

Le variabili di ambiente possono essere usate per fornire alcune informazioni di configurazione in fase di esecuzione. Le manopole di configurazione specificate come variabili di ambiente in genere hanno il prefisso **COMPlus_** .

È possibile definire le variabili di ambiente dal pannello di controllo di Windows, dalla riga di comando o a livello di codice chiamando il metodo <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> nei sistemi basati su Windows e UNIX.

Gli esempi seguenti illustrano come impostare una variabile di ambiente dalla riga di comando:

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
