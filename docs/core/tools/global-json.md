---
title: panoramica di global.json
description: Informazioni su come usare il file global.json per impostare la versione di .NET Core SDK durante l'esecuzione dei comandi dell'interfaccia della riga di comando di .NET Core.
ms.date: 01/14/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 70257566e1ff30f5c97212a5e0e3c308c27738b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625995"
---
# <a name="globaljson-overview"></a>panoramica di global.json

**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive

Il file *global.json* consente di definire la versione di .NET Core SDK usata quando si eseguono comandi dell'interfaccia della riga di comando di .NET Core. La selezione di .NET Core SDK è indipendente dalla specifica del runtime delle destinazioni del progetto. La versione di .NET Core SDK indica quali versioni dell'interfaccia della riga di comando di .NET Core viene utilizzata.

In generale, si desidera utilizzare la versione più recente degli strumenti SDK, pertanto non è necessario alcun file *global.json.* In alcuni scenari avanzati, è possibile controllare la versione degli strumenti SDK e in questo articolo viene illustrato come eseguire questa operazione.

Per altre informazioni su come specificare il runtime, vedere [Framework di destinazione](../../standard/frameworks.md).

.NET Core SDK cerca un file *global.json* nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.

## <a name="globaljson-schema"></a>schema global.json

### <a name="sdk"></a>SDK

Digitare: `object`

Specifica le informazioni sul .NET Core SDK da selezionare.

#### <a name="version"></a>version

- Digitare: `string`

- Disponibile da: .NET Core 1.0 SDK.

La versione del .NET Core SDK da usare.

Questo campo:

- Non dispone del supporto per i caratteri jolly, ovvero è necessario specificare il numero di versione completo.
- Non supporta gli intervalli di versione.

#### <a name="allowprerelease"></a>allowPrerelease

- Digitare: `boolean`

- Disponibile da: .NET Core 3.0 SDK.

Indica se il sistema di risoluzione SDK deve considerare le versioni non definitive quando si seleziona la versione dell'SDK da utilizzare.

Se non si imposta questo valore in modo esplicito, il valore predefinito dipende se si esegue da Visual Studio:If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:

- Se **non** si è in Visual Studio, il valore predefinito è `true`.
- Se ci si trova in Visual Studio, viene utilizzato lo stato di versione non definitiva richiesto. Ovvero, se si utilizza una versione di anteprima di Visual Studio o si imposta l'opzione **Usa anteprime di .NET Core SDK** (in **Strumenti** > **Opzioni opzioni** > **dell'ambiente** > Preview**Features**), il valore predefinito è `true`; in `false`caso contrario, .

#### <a name="rollforward"></a>rollForward

- Digitare: `string`

- Disponibile da: .NET Core 3.0 SDK.

Criteri di rollforward da utilizzare quando si seleziona una versione SDK, come fallback quando manca una versione specifica dell'SDK o come direttiva per l'utilizzo di una versione superiore. Una [versione](#version) deve essere `rollForward` specificata con un valore, `latestMajor`a meno che non venga impostato su .

Per comprendere i criteri disponibili e il relativo comportamento, `x.y.znn`considerare le seguenti definizioni per una versione SDK nel formato:

- `x`è la versione principale.
- `y`è la versione secondaria.
- `z`è la banda di funzionalità.
- `nn`è la versione della patch.

Nella tabella seguente vengono illustrati `rollForward` i valori possibili per la chiave:

| valore         | Comportamento |
| ------------- | ---------- |
| `patch`       | Utilizza la versione specificata. <br> Se non viene trovato, passa all'ultimo livello di patch. <br> Se non viene trovato, ha esito negativo. <br><br> Questo valore è il comportamento legacy delle versioni precedenti dell'SDK. |
| `feature`     | Utilizza il livello di patch più recente per la banda principale, secondaria e caratteristica specificata. <br> Se non viene trovato, passa alla banda di funzionalità superiore successiva all'interno dello stesso major/minore e utilizza il livello di patch più recente per tale feature band. <br> Se non viene trovato, ha esito negativo. |
| `minor`       | Utilizza il livello di patch più recente per la banda principale, secondaria e caratteristica specificata. <br> Se non viene trovato, passa alla banda di funzionalità superiore successiva all'interno della stessa versione principale/secondaria e utilizza il livello di patch più recente per tale feature band. <br> Se non viene trovato, passa alla banda secondaria secondaria minore e caratteristica all'interno della stessa major e utilizza il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, ha esito negativo. |
| `major`       | Utilizza il livello di patch più recente per la banda principale, secondaria e caratteristica specificata. <br> Se non viene trovato, passa alla banda di funzionalità superiore successiva all'interno della stessa versione principale/secondaria e utilizza il livello di patch più recente per tale feature band. <br> Se non viene trovato, passa alla banda secondaria secondaria minore e caratteristica all'interno della stessa major e utilizza il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, passa alla banda maggiore, secondaria e caratteristica superiore successiva e utilizza il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, ha esito negativo. |
| `latestPatch` | Utilizza l'ultimo livello di patch installato che corrisponde alla banda principale, secondaria e di funzionalità richiesta con un livello di patch maggiore o uguale al valore specificato. <br> Se non viene trovato, ha esito negativo. |
| `latestFeature` | Utilizza la banda di funzionalità e il livello di patch più elevati installati che corrispondono a quelli richiesti maggiore e minore con una banda di funzionalità maggiore o uguale al valore specificato. <br> Se non viene trovato, ha esito negativo. |
| `latestMinor` | Utilizza il livello secondario, banda di funzionalità e livello di patch più alto installato che corrisponde al livello principale richiesto con un minore secondario maggiore o uguale al valore specificato. <br> Se non viene trovato, ha esito negativo. |
| `latestMajor` | Utilizza il più alto .NET Core SDK installato con un'area principale maggiore maggiore o uguale al valore specificato. <br> Se non viene trovato, fallire. |
| `disable`     | Non va avanti. Corrispondenza esatta richiesta. |

## <a name="examples"></a>Esempi

L'esempio seguente mostra come non usare le versioni non definitive:The following example shows how to not use prerelease versions:

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

Nell'esempio seguente viene illustrato come utilizzare la versione più recente installata che è maggiore o uguale alla versione specificata:

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestMajor"
  }
}
```

L'esempio seguente mostra come utilizzare l'esatta versione specificata:

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

Nell'esempio seguente viene illustrato come utilizzare la versione di patch più elevata installata di una versione specifica (nel formato 3.1.1xx):

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a>global.json e interfaccia della riga di comando di .NET Core

È utile sapere quali versioni dell'SDK sono installate nel computer per impostarne una nel file *global.json.* Per ulteriori informazioni su come eseguire questa operazione, vedere [come verificare che .NET Core sia già installato](../install/how-to-detect-installed-versions.md#check-sdk-versions).

Per installare altre versioni di .NET Core SDK nel computer, visitare la pagina [Scarica .NET Core.](https://dotnet.microsoft.com/download/dotnet-core)

È possibile creare un nuovo file *global.json* nella directory corrente eseguendo il comando [dotnet new](dotnet-new.md), in modo simile al seguente esempio:

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a>Regole di corrispondenza

> [!NOTE]
> Le regole di corrispondenza `dotnet.exe` sono regolate dal punto di ingresso, comune a tutti i runtime installati di .NET Core installati. Le regole di corrispondenza per l'ultima versione installata di .NET Core Runtime vengono utilizzate quando si dispone di più runtime installati side-by-side.

## <a name="net-core-3x"></a>[.NET Core 3.x](#tab/netcore3x)

A partire da .NET Core 3.0, si applicano le regole seguenti per determinare la versione dell'SDK da utilizzare:

- Se non viene trovato alcun file *global.json* o *global.json* `allowPrerelease` non specifica una versione SDK né un `rollForward` `latestMajor`valore, viene utilizzata la versione SDK installata più la più alta (equivalente all'impostazione su ). La versione precedente dell'SDK `dotnet` viene considerata dipende da come viene richiamata.
  - Se **non** si è in Visual Studio, vengono considerate le versioni non definitive.
  - Se ci si trova in Visual Studio, viene utilizzato lo stato di versione non definitiva richiesto. Ovvero, se si utilizza una versione di anteprima di Visual Studio o si imposta l'opzione **Usa anteprime di .NET Core SDK** (in **Strumenti** > **Opzioni** > opzioni**dell'ambiente****Environment** > Preview Features ), vengono considerate le versioni di non definitive; in caso contrario, vengono considerate solo le versioni di rilascio.
- Se viene trovato un file *global.json* che non specifica una `allowPrerelease` versione SDK ma specifica un valore, `rollForward` `latestMajor`viene utilizzata la versione SDK installata più alta (equivalente all'impostazione su ). Il fatto che la versione più recente dell'SDK possa essere release o non definitiva dipende dal valore di `allowPrerelease`. `true`indica che vengono considerate le versioni non definitive; `false` indica che vengono considerate solo le versioni di rilascio.
- Se viene trovato un file *global.json* che specifica una versione SDK:

  - Se `rollFoward` non è impostato `latestPatch` alcun valore, viene utilizzato come criterio predefinito. `rollForward` In caso contrario, controllare ogni valore e il relativo comportamento nella sezione [rollForward.](#rollforward)
  - Se le versioni non definitive vengono considerate `allowPrerelease` e qual è il comportamento predefinito quando non è impostato è descritto nella sezione [allowPrerelease.](#allowprerelease)

## <a name="net-core-2x"></a>[.NET Core 2.x](#tab/netcore2x)

In .NET Core 2.x SDK, le regole seguenti si applicano quando si determina la versione dell'SDK da utilizzare:

- Se non vengono trovati file *global.json* o *global.json* non specifica una versione SDK, viene usata l'ultima versione SDK installata. La versione più recente dell'SDK può essere la versione non definitiva o la versione non definitiva: vince il numero di versione più alto.
- Se *global.json* specifica una versione SDK:
  - Se la versione SDK indicata è presente nel computer, si usa quella versione.
  - Se la versione SDK specificata non è presente nel computer, viene usata la **versione patch** SDK installata più recente. L'ultima versione della **patch** SDK installata può essere la versione finale o la versione non definitiva: vince il numero di versione più alto. In .NET Core 2.1 e versioni successive, le **versioni patch** inferiori alla **versione patch** specificata vengono ignorate nella selezione del SDK.
  - Se non è possibile trovare la versione SDK specificata e una **versione patch** SDK appropriata, viene generato un errore.

La versione SDK è composta dalle seguenti parti:

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

La **versione definitiva** di .NET Core SDK è rappresentata dalla prima cifra (`x`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive. In generale, .NET Core SDK ha un ciclo di rilascio più veloce rispetto a .NET Core.

La **versione patch** è definita dalle ultime due cifre (`yz`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive. Ad esempio, se si specifica `2.1.300` come versione SDK, la selezione del SDK può arrivare fino a `2.1.399` ma `2.1.400` non è considerata una versione patch per `2.1.300`.

Le versioni di .NET core SDK da `2.1.100` a `2.1.201` sono state rilasciate durante la transizione tra gli schemi dei numeri di versione e non gestiscono correttamente la notazione `xyz`. Se queste versioni vengono specificate nel file *global.json*, è consigliabile verificare che tali versioni siano presenti nei computer di destinazione.

---

## <a name="troubleshoot-build-warnings"></a>Risolvere i problemi relativi agli avvisi di compilazioneTroubleshoot build

* L'avviso seguente indica che il progetto è stato compilato utilizzando una versione non definitiva di .NET Core SDK:

  > Si sta lavorando con una versione di anteprima di .NET Core SDK. È possibile definire la versione SDK tramite un file global.json nel progetto corrente. Per <https://go.microsoft.com/fwlink/?linkid=869452>saperne di più su .

  Le versioni di .NET Core SDK hanno una storia e un impegno di alta qualità. Tuttavia, se non si vuole usare una versione non definitiva, controllare le diverse strategie che è possibile usare con .NET Core 3.0 SDK o versione successiva nella sezione [allowPrerelease.](#allowprerelease) Per i computer in cui non è mai stato installato un runtime o SDK .NET Core 3.0 o versione successiva, è necessario creare un file *global.json* e specificare la versione esatta che si desidera utilizzare.

* L'avviso seguente indica che il progetto è destinato a EF Core 1.0 o 1.1, che non è compatibile con .NET Core 2.1 SDK e versioni successive:

  > Progetto di avvio '{startupProject}' framework di destinazione '.NETCoreApp' versione '{targetFrameworkVersion}'. Questa versione degli strumenti della riga di comando di Entity Framework Core .NET supporta solo la versione 2.0 o successive. Per informazioni sull'utilizzo di versioni <https://go.microsoft.com/fwlink/?linkid=871254>precedenti degli strumenti, vedere .

  A partire da .NET Core 2.1 SDK (versione 2.1.300), il comando `dotnet ef` è incluso nell'SDK. Per compilare il progetto, installare .NET Core 2.0 SDK (versione 2.1.201) o precedente nel computer e definire la versione SDK desiderata utilizzando il file *global.json.* Per altre informazioni sul comando `dotnet ef`, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).

## <a name="see-also"></a>Vedere anche

- [Come vengono risolti gli SDK di progetto](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
