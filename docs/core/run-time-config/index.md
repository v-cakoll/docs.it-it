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
# <a name="net-core-run-time-configuration-settings"></a>Impostazioni di configurazione della fase di esecuzione di .NET Core

.NET Core supporta l'uso di file di configurazione e variabili di ambiente per configurare il comportamento delle applicazioni .NET Core in fase di esecuzione. La configurazione in fase di esecuzione è un'opzione interessante se:

- Non si è proprietari o si controlla il codice sorgente per un'applicazione e pertanto non è possibile configurarlo a livello di programmazione.

- Più istanze dell'applicazione vengono eseguite contemporaneamente in un unico sistema e si desidera configurare ognuna per ottenere prestazioni ottimali.

> [!NOTE]
> Questa documentazione è un lavoro in corso. Se si nota che le informazioni presentate in questo documento sono incomplete o non accurate, è possibile [aprire un problema](https://github.com/dotnet/docs/issues) per segnalarlo o [inviare una richiesta pull](https://github.com/dotnet/docs/pulls) per risolvere il problema. Per informazioni sull'invio di richieste pull per il repository DotNet/docs, vedere la guida per i [collaboratori](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).

.NET Core fornisce i meccanismi seguenti per la configurazione delle applicazioni in fase di esecuzione:

- Il [file runtimeconfig. JSON](#runtimeconfigjson)

- [Variabili di ambiente](#environment-variables)

Gli articoli di questa sezione della documentazione includono sono organizzati per categoria, ad esempio debug e Garbage Collection. Se applicabile, vengono visualizzate le opzioni di configurazione per *runtimeconfig. JSON* (solo .NET Core), *app. config* (solo .NET Framework) e le variabili di ambiente.

## <a name="runtimeconfigjson"></a>runtimeconfig. JSON

Specificare le opzioni di configurazione in fase di esecuzione nella sezione **configProperties** del file *runtimeconfig. JSON* dell'app. Questa sezione presenta il formato seguente:

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

Di seguito è riportato un esempio di file:

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

Il file *runtimeconfig. JSON* viene creato automaticamente nella directory di compilazione tramite il comando [DotNet Build](../tools/dotnet-build.md) . Viene creato anche quando si seleziona l'opzione di menu **Compila** in Visual Studio. È quindi possibile modificare il file dopo che è stato creato.

Alcuni valori di configurazione possono essere impostati anche a livello di codice chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

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
