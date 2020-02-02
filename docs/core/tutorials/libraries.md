---
title: Sviluppare librerie con la interfaccia della riga di comando di .NET Core
description: Informazioni su come creare librerie .NET Core usando il interfaccia della riga di comando di .NET Core. Si creerà una libreria che supporta più framework.
author: cartermp
ms.date: 05/01/2017
ms.openlocfilehash: a7c0175d29f483571578b58d698dd790cf66f7f4
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920439"
---
# <a name="develop-libraries-with-the-net-core-cli"></a>Sviluppare librerie con la interfaccia della riga di comando di .NET Core

Questo articolo illustra come scrivere librerie per .NET usando il interfaccia della riga di comando di .NET Core. L'interfaccia della riga di comando offre un'esperienza efficace e di basso livello per qualsiasi sistema operativo supportato. È comunque sempre possibile creare librerie con Visual Studio. Se si preferisce questo tipo di esperienza, [consultare la Guida di Visual Studio](library-with-visual-studio.md).

## <a name="prerequisites"></a>Prerequisiti

È necessario che [l'SDK e l'interfaccia della riga di comando di .NET Core](https://dotnet.microsoft.com/download) siano installati nel computer.

Per le sezioni di questo documento relative alle versioni di .NET Framework è necessario avere [.NET Framework](https://dotnet.microsoft.com) installato in un computer Windows.

Inoltre, se si desidera supportare le destinazioni .NET Framework precedenti, è necessario installare Targeting Pack o Developer Pack dalla pagina degli [archivi di download di .NET](https://dotnet.microsoft.com/download/archives). Fare riferimento a questa tabella:

| Versione di .NET Framework | Pacchetto da scaricare                                       |
| ---------------------- | ------------------------------------------------------ |
| 4.6.1                  | .NET Framework 4.6.1 Targeting Pack                    |
| 4.6                    | .NET Framework 4.6 Targeting Pack                      |
| 4.5.2                  | .NET Framework 4.5.2 Developer Pack                    |
| 4.5.1                  | .NET Framework 4.5.1 Developer Pack                    |
| 4.5                    | Windows Software Development Kit per Windows 8         |
| 4.0                    | Windows SDK per Windows 7 e .NET Framework 4         |
| 2.0, 3.0 e 3.5      | Runtime di .NET Framework 3.5 SP1 (o versione per Windows 8 o successiva) |

## <a name="how-to-target-the-net-standard"></a>Come definire .NET Standard come destinazione

Se non si ha familiarità con .NET Standard, vedere [.NET standard](../../standard/net-standard.md) per altre informazioni.

In questo articolo è presente una tabella che esegue il mapping di .NET Standard versioni a diverse implementazioni:

[!INCLUDE [net-standard-table](../../../includes/net-standard-table.md)]

Ecco cosa significa questa tabella ai fini della creazione di una libreria:

La versione di .NET Standard scelta sarà un compromesso tra l'accesso alle API più recenti e la possibilità di definire come destinazione più implementazioni .NET e versioni di .NET Standard. È possibile controllare l'intervallo di piattaforme e versioni di destinazione selezionando una versione di `netstandardX.X` (dove `X.X` è un numero di versione) e aggiungendola al file di progetto (`.csproj` o `.fsproj`).

Sono disponibili tre opzioni principali per la definizione delle .NET Standard, a seconda delle esigenze.

1. È possibile usare la versione predefinita di .NET Standard fornita da modelli, `netstandard1.4`, che consente di accedere alla maggior parte delle API in .NET Standard pur essendo ancora compatibili con UWP, .NET Framework 4.6.1 e .NET Standard 2,0.

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. È possibile usare una versione precedente o superiore di .NET Standard modificando il valore nel nodo `TargetFramework` del file di progetto.

    Le versioni di .NET Standard sono compatibili con le versioni precedenti. Ciò significa che le librerie `netstandard1.0` possono essere eseguite su piattaforme `netstandard1.1` e versioni successive. Tuttavia, non esiste alcuna compatibilità con le edizioni. Le piattaforme .NET Standard inferiori non possono fare riferimento a quelle più elevate. Ciò significa che le librerie `netstandard1.0` non possono fare riferimento alle librerie `netstandard1.1` o versioni successive. Selezionare la versione di .NET Standard che contiene la combinazione di API e supporto per piattaforme più adatta alle proprie esigenze. Attualmente è consigliabile selezionare `netstandard1.4`.

3. Se si vuole usare come destinazione .NET Framework versioni 4,0 o successive oppure si vuole usare un'API disponibile in .NET Framework ma non in .NET Standard (ad esempio `System.Drawing`), leggere le sezioni seguenti e informazioni su come eseguire la multitargeting.

## <a name="how-to-target-net-framework"></a>Come definire come destinazione .NET Framework

> [!NOTE]
> Queste istruzioni presuppongono che nel computer sia installato .NET Framework. Vedere la sezione [Prerequisiti](#prerequisites) per informazioni sulle dipendenze da installare.

Tenere presente che alcune delle .NET Framework versioni usate in questo argomento non sono più supportate. Per informazioni sulle versioni non supportate, vedere [Domande frequenti sui criteri relativi al ciclo di vita del supporto per Microsoft .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us).

Se si vuole raggiungere il numero massimo di sviluppatori e progetti, usare .NET Framework 4,0 come destinazione della linea di base. Per .NET Framework di destinazione, iniziare usando il moniker del Framework di destinazione corretto (TFM) che corrisponde alla versione di .NET Framework che si vuole supportare.

| Versione di .NET Framework | Moniker framework di destinazione      |
| ---------------------- | -------- |
| .NET Framework 2.0     | `net20`  |
| .NET Framework 3.0     | `net30`  |
| .NET Framework 3.5     | `net35`  |
| .NET Framework 4.0     | `net40`  |
| .NET Framework 4.5     | `net45`  |
| .NET Framework 4.5.1   | `net451` |
| .NET Framework 4.5.2   | `net452` |
| .NET Framework 4.6     | `net46`  |
| .NET Framework 4.6.1   | `net461` |
| .NET Framework 4.6.2   | `net462` |
| .NET Framework 4.7     | `net47`  |
| .NET Framework 4.8     | `net48`  |

Quindi inserire il TFM nella sezione `TargetFramework` del file di progetto. Ad esempio, ecco come scrivere una libreria destinata a .NET Framework 4,0:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

L'operazione è ora completata. Anche se questa operazione è stata compilata solo per .NET Framework 4, è possibile usare la libreria nelle versioni più recenti di .NET Framework.

## <a name="how-to-multitarget"></a>Come definire più destinazioni

> [!NOTE]
> Le istruzioni seguenti presuppongono che nel computer sia installato .NET Framework. Vedere la sezione [Prerequisiti](#prerequisites) per informazioni sulle dipendenze da installare e sull'area da cui scaricarle.

Quando il progetto supporta sia .NET Framework che .NET Core, può essere opportuno definire come destinazione le versioni precedenti di .NET Framework. In questo scenario, per usare API e costrutti di linguaggio più recenti per le destinazioni più recenti, inserire direttive `#if` nel codice. Può anche essere necessario aggiungere diversi pacchetti e dipendenze per ogni piattaforma di destinazione per includere le diverse API necessarie per ogni caso.

Si supponga ad esempio di avere una libreria che esegue operazioni di rete tramite HTTP. Per .NET Standard e .NET Framework 4.5 o versioni successive, è possibile usare la classe `HttpClient` dello spazio dei nomi `System.Net.Http`. Tuttavia, le versioni precedenti di .NET Framework non dispongono della classe `HttpClient` e per tali versioni è quindi possibile usare in alternativa la classe `WebClient` dello spazio dei nomi `System.Net`.

Il file di progetto può avere un aspetto simile al seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

Si noteranno tre modifiche principali:

1. Il nodo `TargetFramework` è stato sostituito da `TargetFrameworks` e all'interno sono espressi tre TFM.
1. Un nodo `<ItemGroup>` per la destinazione `net40` chiama un riferimento di .NET Framework.
1. Un nodo `<ItemGroup>` per la destinazione `net45` chiama due riferimenti di .NET Framework.

Il sistema di compilazione è in grado di riconoscere i seguenti simboli di preprocessore usati nelle direttive `#if`:

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

Ecco un esempio che usa la compilazione condizionale basata sulla destinazione:

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "https://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

Se si compila il progetto con `dotnet build` si noteranno tre directory sotto la cartella `bin/`:

```
net40/
net45/
netstandard1.4/
```

Ogni directory contiene i file `.dll` per ciascuna destinazione.

## <a name="how-to-test-libraries-on-net-core"></a>Come testare le librerie in .NET Core

È importante essere in grado di eseguire test tra diverse piattaforme. È possibile usare [xUnit](https://xunit.github.io/) o MSTest senza modifiche. Entrambi sono adatti per gli unit test della libreria in .NET Core. La modalità di configurazione della soluzione con progetti di test dipende dalla [struttura della soluzione](#structuring-a-solution). Nell'esempio seguente si presuppone che le directory di test e di origine si trovino nella stessa directory di livello superiore.

> [!NOTE]
> Questa operazione usa alcuni comandi [interfaccia della riga di comando di .NET Core](../tools/index.md) . Per altre informazioni, vedere [dotnet new](../tools/dotnet-new.md) e [dotnet sln](../tools/dotnet-sln.md).

1. Configurare la soluzione. È possibile farlo con i comandi seguenti:

   ```bash
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   I progetti vengono creati e collegati in una soluzione. La directory per `SolutionWithSrcAndTest` ha un aspetto simile al seguente:

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. Passare alla directory del progetto di test e aggiungere un riferimento a `MyProject.Test` da `MyProject`.

   ```bash
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. Ripristinare i pacchetti e compilare i progetti:

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

1. Verificare che xUnit sia in esecuzione con il comando `dotnet test`. Se si sceglie di usare MSTest, va invece eseguita l'utilità di test delle console MSTest.

L'operazione è ora completata. È ora possibile testare la libreria in tutte le piattaforme usando gli strumenti da riga di comando. Una volta completata la configurazione, è possibile procedere con il testing della libreria in modo molto semplice:

1. Eseguire le opportune modifiche nella libreria.
1. Eseguire i test dalla riga di comando, nella directory di test, usando il comando `dotnet test`.

Il codice viene ricompilato automaticamente quando si richiama il comando `dotnet test`.

## <a name="how-to-use-multiple-projects"></a>Come usare più progetti

Per le librerie di maggiori dimensioni, è spesso necessario inserire funzionalità in progetti diversi.

Si supponga di voler creare una libreria che può essere utilizzata in modo C# idiomatiche F#e. Ciò significa che i consumer della libreria lo utilizzeranno in modi che sono naturali C# per F#o. In C#, ad esempio, la libreria può essere utilizzata in un modo simile al seguente:

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

In F#, invece, può assumere l'aspetto seguente:

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

Scenari di utilizzo come questo indicano che le API a cui si accede devono avere una struttura diversa per C# e F#.  Un approccio comune per gestire questa situazione consiste nel definire l'intera logica di una libreria in un progetto di base, a cui eseguono chiamate i livelli di API definiti nei progetti C# e F#.  Nella parte restante della sezione verranno usati i nomi seguenti:

* **AwesomeLibrary. Core** : un progetto di base che contiene tutta la logica per la libreria
* **AwesomeLibrary.CSharp**: un progetto con API pubbliche destinato all'utilizzo in C#
* **AwesomeLibrary.FSharp**: un progetto con API pubbliche destinato all'utilizzo in F#

Eseguire i seguenti comandi nel terminale in uso per ottenere la stessa struttura mostrata in questa Guida:

```console
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

In questo modo vengono aggiunti i tre progetti precedenti e un file di soluzione che li collega insieme. La creazione del file della soluzione e dei progetti di collegamento consentirà di ripristinare e compilare progetti da un livello superiore.

### <a name="project-to-project-referencing"></a>Definizione di riferimenti da progetto a progetto

Il modo migliore per creare un riferimento a un progetto è l'uso dell'interfaccia della riga di comando di .NET Core per aggiungere un riferimento al progetto. Dalle directory di progetto **AwesomeLibrary.CSharp** e **AwesomeLibrary.FSharp** è possibile eseguire il comando seguente:

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

I file di progetto per **AwesomeLibrary.CSharp** e **AwesomeLibrary.FSharp** includeranno ora un riferimento a **AwesomeLibrary.Core** come destinazione `ProjectReference`.  È possibile verificare la presenza del riferimento cercando quanto segue nei file di progetto:

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

Se si preferisce non usare l'interfaccia della riga di comando .NET Core, è possibile aggiungere manualmente questa sezione a ogni file di progetto.

### <a name="structuring-a-solution"></a>Definizione della struttura di una soluzione

Un altro aspetto importante delle soluzioni basate su più progetti è quello di stabilire una buona struttura complessiva dei progetti. È possibile organizzare il codice come desiderato. A condizione che si colleghi ogni progetto al file di soluzione mediante `dotnet sln add`, sarà possibile eseguire `dotnet restore` e `dotnet build` a livello della soluzione.
