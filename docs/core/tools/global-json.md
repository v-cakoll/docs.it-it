---
title: panoramica di global.json
description: Informazioni su come usare il file global.json per impostare la versione di .NET Core SDK durante l'esecuzione dei comandi dell'interfaccia della riga di comando di .NET Core.
ms.date: 01/14/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 8582c495be58e38ca19320f14e20f8c511a9c821
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920503"
---
# <a name="globaljson-overview"></a>panoramica di global.json

**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive

Il file *global.json* consente di definire la versione di .NET Core SDK usata quando si eseguono comandi dell'interfaccia della riga di comando di .NET Core. La selezione di .NET Core SDK è indipendente dalla specifica del runtime delle destinazioni del progetto. La versione .NET Core SDK indica le versioni di interfaccia della riga di comando di .NET Core utilizzate.

In generale, si vuole usare la versione più recente degli strumenti SDK, pertanto non è necessario alcun file *Global. JSON* . In alcuni scenari avanzati, potrebbe essere necessario controllare la versione degli strumenti SDK e in questo articolo viene illustrato come eseguire questa operazione.

Per altre informazioni su come specificare il runtime, vedere [Framework di destinazione](../../standard/frameworks.md).

.NET Core SDK cerca un file *global.json* nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.

## <a name="globaljson-schema"></a>schema global.json

### <a name="sdk"></a>SDK

Tipo: `object`

Specifica le informazioni sul .NET Core SDK da selezionare.

#### <a name="version"></a>Versione di

- Tipo: `string`

- Disponibile a partire da: .NET Core 1,0 SDK.

La versione del .NET Core SDK da usare.

Questo campo:

- Non dispone del supporto per i caratteri jolly, ovvero è necessario specificare il numero di versione completo.
- Non supporta gli intervalli di versione.

#### <a name="allowprerelease"></a>Flag allowprerelease

- Tipo: `boolean`

- Disponibile a partire da: .NET Core 3,0 SDK.

Indica se il resolver SDK deve prendere in considerazione le versioni provvisorie quando si seleziona la versione dell'SDK da usare.

Se questo valore non viene impostato in modo esplicito, il valore predefinito varia a seconda che l'esecuzione venga eseguita da Visual Studio:

- Se **non** si è in Visual Studio, il valore predefinito è `true`.
- Se si usa Visual Studio, viene usato lo stato della versione non definitiva richiesta. Ovvero, se si usa una versione di anteprima di Visual Studio o si imposta l'opzione **Usa anteprime del .NET Core SDK** (in **strumenti** > **Opzioni** > le funzionalità dell' **ambiente** > **Anteprima**), il valore predefinito è `true`; in caso contrario, `false`.

#### <a name="rollforward"></a>rollForward

- Tipo: `string`

- Disponibile a partire da: .NET Core 3,0 SDK.

Criteri di rollforward da usare quando si seleziona una versione di SDK, come fallback quando manca una versione specifica dell'SDK o come direttiva per usare una versione successiva. È necessario specificare una [versione](#version) con un valore `rollForward`, a meno che non lo si stia impostando su `latestMajor`.

Per comprendere i criteri disponibili e il relativo comportamento, prendere in considerazione le seguenti definizioni per una versione SDK nel formato `x.y.znn`:

- `x` è la versione principale.
- `y` è la versione secondaria.
- `z` è la banda della funzionalità.
- `nn` è la versione della patch.

La tabella seguente mostra i valori possibili per la chiave di `rollForward`:

| Valore         | Comportamento di |
| ------------- | ---------- |
| `patch`       | Usa la versione specificata. <br> Se non viene trovato, viene eseguito il rollforward al livello di patch più recente. <br> Se non viene trovato, ha esito negativo. <br><br> Questo valore è il comportamento legacy delle versioni precedenti dell'SDK. |
| `feature`     | Usa il livello di patch più recente per la banda principale, secondaria e di funzionalità specificata. <br> Se non viene trovato, viene eseguito il rollforward alla successiva fascia di funzionalità superiore all'interno della stessa major/minor e viene usato il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, ha esito negativo. |
| `minor`       | Usa il livello di patch più recente per la banda principale, secondaria e di funzionalità specificata. <br> Se non viene trovato, viene eseguito il rollforward alla successiva fascia di funzionalità superiore all'interno della stessa versione principale/secondaria e viene usato il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, viene eseguito il rollforward alla successiva fascia secondaria e di funzionalità più alta all'interno della stessa entità e utilizza il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, ha esito negativo. |
| `major`       | Usa il livello di patch più recente per la banda principale, secondaria e di funzionalità specificata. <br> Se non viene trovato, viene eseguito il rollforward alla successiva fascia di funzionalità superiore all'interno della stessa versione principale/secondaria e viene usato il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, viene eseguito il rollforward alla successiva fascia secondaria e di funzionalità più alta all'interno della stessa entità e utilizza il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, viene eseguito il rollforward alla successiva fascia principale, secondaria e di funzionalità più alta e viene usato il livello di patch più recente per tale banda di funzionalità. <br> Se non viene trovato, ha esito negativo. |
| `latestPatch` | Usa il livello di patch installato più recente che corrisponde alla banda principale, secondaria e di funzionalità richiesta con un livello di patch e che è maggiore o uguale al valore specificato. <br> Se non viene trovato, ha esito negativo. |
| `latestFeature` | Usa la banda di funzionalità e il livello di patch più elevati che corrispondono al principale e al minore richiesti con una banda di funzionalità maggiore o uguale al valore specificato. <br> Se non viene trovato, ha esito negativo. |
| `latestMinor` | Usa la versione secondaria, la banda di funzionalità e il livello di patch più elevati che corrispondono al principale richiesto con un valore secondario maggiore o uguale al valore specificato. <br> Se non viene trovato, ha esito negativo. |
| `latestMajor` | Usa la .NET Core SDK installata più alta con una maggiore o uguale al valore specificato. <br> Se non viene trovato, ha esito negativo. |
| `disable`     | Il rollforward non viene eseguito. È necessaria una corrispondenza esatta. |

## <a name="examples"></a>Esempi

Nell'esempio seguente viene illustrato come non utilizzare le versioni provvisorie:

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

Nell'esempio seguente viene illustrato come utilizzare la versione esatta specificata:

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

L'esempio seguente illustra come usare la versione patch più recente installata di una versione specifica (nel formato 3.1.1 XX):

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a>global.json e interfaccia della riga di comando di .NET Core

È utile comprendere quali versioni dell'SDK sono installate nel computer per impostarne una nel file *Global. JSON* . Per altre informazioni su come eseguire questa operazione, vedere [come verificare che .NET Core sia già installato](../install/how-to-detect-installed-versions.md#check-sdk-versions).

Per installare altre versioni .NET Core SDK nel computer, visitare la pagina [download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .

È possibile creare un nuovo file *global.json* nella directory corrente eseguendo il comando [dotnet new](dotnet-new.md), in modo simile al seguente esempio:

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a>Regole di corrispondenza

> [!NOTE]
> Le regole di corrispondenza sono regolate dal punto di ingresso `dotnet.exe`, che è comune in tutti i runtime installati di .NET Core installati. Le regole di corrispondenza per la versione installata più recente del runtime di .NET Core vengono usate quando si hanno più runtime installati side-by-side.

## <a name="net-core-3xtabnetcore3x"></a>[.NET Core 3. x](#tab/netcore3x)

A partire da .NET Core 3,0, quando si determina la versione dell'SDK da usare sono valide le regole seguenti:

- Se non viene trovato alcun file *Global. JSON* oppure il file *Global. JSON* non specifica una versione dell'SDK né un valore di `allowPrerelease`, viene usata la versione più recente dell'SDK installata (equivalente all'impostazione di `rollForward` per `latestMajor`). La possibilità di prendere in considerazione le versioni di versione non definitiva dell'SDK dipende dalla modalità di chiamata `dotnet`.
  - Se **non** si è in Visual Studio, vengono considerate le versioni provvisorie.
  - Se si usa Visual Studio, viene usato lo stato della versione non definitiva richiesta. Ovvero, se si usa una versione di anteprima di Visual Studio o si imposta l'opzione **USA** anteprime dell'opzione .NET Core SDK (in **strumenti** > **Opzioni** > le funzionalità dell' **ambiente** > **Anteprima**), vengono considerate le versioni preliminari. in caso contrario, vengono considerate solo le versioni di rilascio.
- Se viene trovato un file *Global. JSON* che non specifica una versione dell'SDK, ma specifica un valore `allowPrerelease`, viene usata la versione più recente dell'SDK installato (equivalente all'impostazione di `rollForward` per `latestMajor`). Se la versione più recente dell'SDK può essere release o la versione preliminare dipende dal valore di `allowPrerelease`. `true` indica che vengono considerate le versioni provvisorie. `false` indica che vengono considerate solo le versioni di rilascio.
- Se viene trovato un file *Global. JSON* che specifica una versione dell'SDK:

  - Se non è impostato alcun valore `rollFoward`, viene utilizzato `latestPatch` come criterio di `rollForward` predefinito. In caso contrario, controllare ogni valore e il relativo comportamento nella sezione [rollforward](#rollforward) .
  - Se vengono considerate le versioni non definitive e qual è il comportamento predefinito quando `allowPrerelease` non è impostato è descritto nella sezione [flag allowprerelease](#allowprerelease) .

## <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

In .NET Core 2. x SDK, quando si determina la versione dell'SDK da usare, si applicano le regole seguenti:

- Se non vengono trovati file *global.json* o *global.json* non specifica una versione SDK, viene usata l'ultima versione SDK installata. La versione più recente dell'SDK può essere release o prerelease. il numero di versione più alto prevale.
- Se *global.json* specifica una versione SDK:
  - Se la versione SDK indicata è presente nel computer, si usa quella versione.
  - Se la versione SDK specificata non è presente nel computer, viene usata la **versione patch** SDK installata più recente. La versione più recente della **patch** SDK installata può essere release o versione preliminare-il numero di versione più alto prevale. In .NET Core 2.1 e versioni successive, le **versioni patch** inferiori alla **versione patch** specificata vengono ignorate nella selezione del SDK.
  - Se non è possibile trovare la versione SDK specificata e una **versione patch** SDK appropriata, viene generato un errore.

La versione dell'SDK è costituita dalle parti seguenti:

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

La **versione definitiva** di .NET Core SDK è rappresentata dalla prima cifra (`x`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive. In generale, .NET Core SDK ha un ciclo di rilascio più veloce rispetto a .NET Core.

La **versione patch** è definita dalle ultime due cifre (`yz`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive. Ad esempio, se si specifica `2.1.300` come versione SDK, la selezione del SDK può arrivare fino a `2.1.399` ma `2.1.400` non è considerata una versione patch per `2.1.300`.

Le versioni di .NET core SDK da `2.1.100` a `2.1.201` sono state rilasciate durante la transizione tra gli schemi dei numeri di versione e non gestiscono correttamente la notazione `xyz`. Se queste versioni vengono specificate nel file *global.json*, è consigliabile verificare che tali versioni siano presenti nei computer di destinazione.

---

## <a name="troubleshooting-build-warnings"></a>Risoluzione dei problemi relativi agli avvisi di compilazione

> [!WARNING]
> Si sta lavorando con una versione di anteprima di .NET Core SDK. È possibile definire la versione SDK tramite un file global.json nel progetto corrente. Per altre informazioni, vedere <https://go.microsoft.com/fwlink/?linkid=869452>

Questo avviso indica che il progetto è stato compilato utilizzando una versione provvisoria del .NET Core SDK. Le versioni di .NET Core SDK hanno una storia e un impegno di alta qualità. Tuttavia, se non si vuole usare una versione provvisoria, controllare le diverse strategie che è possibile usare con .NET Core 3,0 SDK o una versione successiva nella sezione [flag allowprerelease](#allowprerelease) . Per i computer in cui non è mai stato installato un runtime o un SDK di .NET Core 3,0 o versione successiva, è necessario creare un file *Global. JSON* e specificare la versione esatta che si vuole usare.

> [!WARNING]
> Progetto di avvio '{startupProject}' framework di destinazione '.NETCoreApp' versione '{targetFrameworkVersion}'. Questa versione degli strumenti della riga di comando di Entity Framework Core .NET supporta solo la versione 2.0 o successive. Per informazioni sull'uso di versioni precedenti degli strumenti, vedere <https://go.microsoft.com/fwlink/?linkid=871254>

A partire da .NET Core 2.1 SDK (versione 2.1.300), il comando `dotnet ef` è incluso nell'SDK. Questo avviso indica che il progetto è destinato a EF Core 1.0 o 1.1, che non è compatibile con .NET Core 2.1 SDK e versioni successive. Per compilare il progetto, installare .NET Core 2.0 SDK (versione 2.1.201) e versioni precedenti nel computer e definire la versione dell'SDK desiderata usando il file *global.json*. Per altre informazioni sul comando `dotnet ef`, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).

## <a name="see-also"></a>Vedere anche

- [Come vengono risolti gli SDK di progetto](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
