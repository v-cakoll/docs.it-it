---
title: panoramica di global.json
description: Informazioni su come usare il file global.json per impostare la versione di .NET Core SDK durante l'esecuzione dei comandi dell'interfaccia della riga di comando di .NET Core.
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 4da703266e98b209cdd031f4ea856b4d7c83930c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714165"
---
# <a name="globaljson-overview"></a>panoramica di global.json

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

Il file *global.json* consente di definire la versione di .NET Core SDK usata quando si eseguono comandi dell'interfaccia della riga di comando di .NET Core. La selezione di .NET Core SDK è indipendente dalla specifica del runtime delle destinazioni del progetto. La versione di .NET Core SDK indica quali versioni degli strumenti dell'interfaccia della riga di comando di .NET Core vengono usate. In generale, si desidera usare la versione più recente degli strumenti, quindi il file *global.json* non è necessario.

Per altre informazioni su come specificare il runtime, vedere [Framework di destinazione](../../standard/frameworks.md).

.NET Core SDK cerca un file *global.json* nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.

## <a name="globaljson-schema"></a>schema global.json

### <a name="sdk"></a>SDK

Tipo: Object

Specifica le informazioni sul .NET Core SDK da selezionare.

#### <a name="version"></a>Versione di

Tipo: String

La versione del .NET Core SDK da usare.

Si noti che questo campo:

- Non dispone di supporto di caratteri jolly, vale a dire che è necessario specificare il numero di versione completo.
- Non supporta gli intervalli di versione.

L'esempio seguente illustra il contenuto di un file *global.json*:

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a>global.json e interfaccia della riga di comando di .NET Core

È utile sapere quali versioni sono disponibili per configurarne una nel file *global.json*. È possibile trovare l'elenco completo degli SDK disponibili supportati nella pagina [scaricare .NET Core](https://dotnet.microsoft.com/download/dotnet-core) . A partire da .NET Core 2.1 SDK, è possibile eseguire il comando seguente per verificare quali versioni dell'SDK sono già installate nel computer:

```dotnetcli
dotnet --list-sdks
```

Per installare altre versioni .NET Core SDK nel computer, visitare la pagina [download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .

È possibile creare un nuovo file *global.json* nella directory corrente eseguendo il comando [dotnet new](dotnet-new.md), in modo simile al seguente esempio:

```dotnetcli
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a>Regole di corrispondenza

> [!NOTE]
> Le regole di corrispondenza sono regolate da apphost, che fa parte del runtime di .NET Core.
> Quando si dispone di più runtime installati side-by-side, viene usata la versione più recente dell'host.

A partire da .NET Core 2.0, le regole seguenti si applicano per stabilire quale versione SDK usare:

- Se non vengono trovati file *global.json* o *global.json* non specifica una versione SDK, viene usata l'ultima versione SDK installata. L'ultima versione SDK può essere rilasciata o pre-rilasciata: il numero di versione più alto ha la priorità.
- Se *global.json* specifica una versione SDK:
  - Se la versione SDK indicata è presente nel computer, si usa quella versione.
  - Se la versione SDK specificata non è presente nel computer, viene usata la **versione patch** SDK installata più recente. L'ultima **versione patch** SDK installata può essere rilasciata o pre-rilasciata: il numero di versione più alto ha la priorità. In .NET Core 2.1 e versioni successive, le **versioni patch** inferiori alla **versione patch** specificata vengono ignorate nella selezione del SDK.
  - Se non è possibile trovare la versione SDK specificata e una **versione patch** SDK appropriata, viene generato un errore.

La versione SDK è attualmente costituita dalle parti seguenti:

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

La **versione definitiva** di .NET Core SDK è rappresentata dalla prima cifra (`x`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive. In generale, .NET Core SDK ha un ciclo di rilascio più veloce rispetto a .NET Core.

La **versione patch** è definita dalle ultime due cifre (`yz`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive. Ad esempio, se si specifica `2.1.300` come versione SDK, la selezione del SDK può arrivare fino a `2.1.399` ma `2.1.400` non è considerata una versione patch per `2.1.300`.

Le versioni di .NET core SDK da `2.1.100` a `2.1.201` sono state rilasciate durante la transizione tra gli schemi dei numeri di versione e non gestiscono correttamente la notazione `xyz`. Se queste versioni vengono specificate nel file *global.json*, è consigliabile verificare che tali versioni siano presenti nei computer di destinazione.

Con .NET Core SDK 1.x, se è stata specificata una versione e non è stata trovata alcuna corrispondenza esatta, è stata usata la versione SDK più recente. L'ultima versione SDK può essere rilasciata o pre-rilasciata: il numero di versione più alto ha la priorità.

## <a name="troubleshooting-build-warnings"></a>Risoluzione dei problemi relativi agli avvisi di compilazione

> [!WARNING]
> Si sta lavorando con una versione di anteprima di .NET Core SDK. È possibile definire la versione SDK tramite un file global.json nel progetto corrente. Per altre informazioni, vedere <https://go.microsoft.com/fwlink/?linkid=869452>

Questo avviso indica che il progetto è stato compilato usando una versione di anteprima di .NET Core SDK, come illustrato nella sezione [Regole di corrispondenza](#matching-rules). Le versioni di .NET Core SDK hanno una storia e un impegno di alta qualità. Tuttavia, se non si vuole usare una versione di anteprima, aggiungere un file *global.json* alla struttura gerarchica del progetto per specificare la versione SDK da usare e selezionare `dotnet --list-sdks` per confermare che la versione è installata nel computer. Quando viene rilasciata una nuova versione, usare la nuova versione, rimuovere il file *global.json* o aggiornarlo per usare la versione più recente.

> [!WARNING]
> Progetto di avvio '{startupProject}' framework di destinazione '.NETCoreApp' versione '{targetFrameworkVersion}'. Questa versione degli strumenti della riga di comando di Entity Framework Core .NET supporta solo la versione 2.0 o successive. Per informazioni sull'uso di versioni precedenti degli strumenti, vedere <https://go.microsoft.com/fwlink/?linkid=871254>

A partire da .NET Core 2.1 SDK (versione 2.1.300), il comando `dotnet ef` è incluso nell'SDK. Questo avviso indica che il progetto è destinato a EF Core 1.0 o 1.1, che non è compatibile con .NET Core 2.1 SDK e versioni successive. Per compilare il progetto, installare .NET Core 2.0 SDK (versione 2.1.201) e versioni precedenti nel computer e definire la versione dell'SDK desiderata usando il file *global.json*. Per altre informazioni sul comando `dotnet ef`, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).

## <a name="see-also"></a>Vedere anche

- [Come vengono risolti gli SDK di progetto](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
