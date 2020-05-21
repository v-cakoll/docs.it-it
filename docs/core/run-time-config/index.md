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
# <a name="net-core-run-time-configuration-settings"></a>Impostazioni di configurazione della fase di esecuzione di .NET Core

.NET Core supporta l'uso di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione. La configurazione in fase di esecuzione è un'opzione interessante se:

- Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di programmazione.

- Più istanze dell'applicazione vengono eseguite contemporaneamente in un unico sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.

> [!NOTE]
> Questa documentazione è un lavoro in corso. Se si nota che le informazioni presentate in questo documento sono incomplete o non accurate, è possibile [aprire un problema](https://github.com/dotnet/docs/issues) per segnalarlo o [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema. Per informazioni sull'invio di richieste pull per il repository DotNet/docs, vedere la guida per i [collaboratori](https://docs.microsoft.com/contribute/dotnet/dotnet-contribute).

.NET Core fornisce i meccanismi seguenti per configurare il comportamento dell'applicazione in fase di esecuzione:

- Il [file runtimeconfig. JSON](#runtimeconfigjson)

- [Proprietà di MSBuild](#msbuild-properties)

- [Variabili di ambiente](#environment-variables)

> [!TIP]
> La configurazione di un'opzione della fase di esecuzione tramite una variabile di ambiente applica l'impostazione a tutte le app .NET Core. La configurazione di un'opzione in fase di esecuzione nel file *runtimeconfig. JSON* o di progetto applica l'impostazione solo a tale applicazione.

Alcuni valori di configurazione possono essere impostati anche a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo.

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

Se si posizionano le opzioni nel file JSON di output, nidificarle nella `runtimeOptions` Proprietà.

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

Se si stanno inserendo le opzioni nel file JSON del modello, omettere la `runtimeOptions` Proprietà.

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

Le proprietà di MSBuild per la configurazione del comportamento in fase di esecuzione sono indicate nei singoli articoli per ogni area, ad esempio [Garbage Collection](garbage-collector.md). Sono inoltre elencate nella sezione relativa alla configurazione della fase di [esecuzione](../project-sdk/msbuild-props.md#run-time-configuration-properties) del riferimento alle proprietà di MSBuild per i progetti in stile SDK.

## <a name="environment-variables"></a>Variabili di ambiente

Le variabili di ambiente possono essere usate per fornire alcune informazioni di configurazione in fase di esecuzione. La configurazione di un'opzione della fase di esecuzione tramite una variabile di ambiente applica l'impostazione a tutte le app .NET Core. Le manopole di configurazione specificate come variabili di ambiente in genere hanno il prefisso **COMPlus_**.

È possibile definire le variabili di ambiente dal pannello di controllo di Windows, dalla riga di comando o a livello di codice chiamando il <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> metodo in entrambi i sistemi basati su Windows e UNIX.

Gli esempi seguenti illustrano come impostare una variabile di ambiente dalla riga di comando:

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
