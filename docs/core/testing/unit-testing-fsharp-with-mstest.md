---
title: "Testing unità di librerie F# in .NET Core usando il test dotnet e MSTest"
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e MSTest.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.topic: article
dev_langs: fsharp
ms.prod: .net-core
ms.openlocfilehash: ad869d6b66ad5d966037a3ef38154fadcfa5978b
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a>Testing unità di librerie F# in .NET Core usando il test dotnet e MSTest

In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità. Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-mstest/) prima di iniziare. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Creazione del progetto di origine

Aprire una finestra della shell. Creare una directory denominata *unit-testing-with-fsharp* in cui archiviare la soluzione.
In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione. Questo rende più semplice gestire sia la libreria di classi che il progetto di unit test.
All'interno della directory della soluzione creare una directory *MathService*. La struttura della directory e dei file fino a questo momento è la seguente:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

Impostare *MathService* come directory corrente ed eseguire [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) per creare il progetto di origine.  Per usare lo sviluppo basato su test (TDD) si creerà un'implementazione non funzionante del servizio matematico:

```fsharp
module MyMath =
    let sumOfSquares xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

Tornare alla directory *unit-test-con-fsharp*. Eseguire [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.

## <a name="creating-the-test-project"></a>Creazione del progetto di test

Creare quindi la directory *MathService.Tests*. Di seguito è illustrata la struttura di directory:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

Impostare *MathService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new mstest -lang F#`](../tools/dotnet-new.md). Ciò crea un progetto di test che usa MSTest come framework di test. Il modello generato configura il Test Runner nel file *MathServiceTests.fsproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti. Nel passaggio precedente `dotnet new` ha aggiunto MSTest e il Runner di MSTest. Aggiungere ora la libreria di classi `MathService` come un'altra dipendenza del progetto. Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../MathService/MathService.fsproj
```

È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) su GitHub.

Il layout della soluzione finale è il seguente:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

Eseguire [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) nella directory *unit-testing-with-fsharp*.

## <a name="creating-the-first-test"></a>Creazione del primo test

L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto. Aprire *Tests.fs* e aggiungere il codice seguente:

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

L'attributo `[<TestClass>]` indica una classe che contiene test. L'attributo `[<TestMethod>]` indica un metodo di test eseguito dal Test Runner. Dalla directory *unit-test-con-fsharp* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test. Il Test Runner di MSTest include il punto d'ingresso del programma per l'esecuzione dei test. `dotnet test` avvia il Test Runner usando il progetto di unit test creato.

Questi due test mostrano i test più semplici superati e non superati. `My test` viene superato e `Fail every time` non viene superato. A questo punto, creare un test per il metodo `sumOfSquares`. Il metodo `sumOfSquares` restituisce la somma dei quadrati di tutti i valori interi dispari che fanno parte della sequenza di input. Anziché tentare di scrivere tutte queste funzioni in una sola volta, è possibile creare in modo iterativo test per la convalida della funzionalità. Fare in modo che ogni test venga superato significa creare le funzionalità necessarie per il metodo.

Il test più semplice che si può scrivere consiste nel chiamare `sumOfSquares` con tutti i numeri pari. In questo caso il risultato dovrebbe essere una sequenza vuota di numeri interi.  Ecco questo test:

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.sumOfSquares [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

Si noti che la sequenza `expected` è stata convertita in elenco. La libreria MSTest si basa su molti tipi .NET standard. Questa dipendenza indica che l'interfaccia pubblica e i risultati previsti supportano <xref:System.Collections.ICollection> invece di <xref:System.Collections.IEnumerable>.

Quando si esegue il test, si noterà che non viene superato. Non è stata ancora creata l'implementazione. Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `Mathservice`:

```csharp
let sumOfSquares xs =
    Seq.empty<int> |> Seq.toList
```

Nella directory *unit-test-con-fsharp* eseguire di nuovo `dotnet test`. Il comando `dotnet test` esegue prima una compilazione del progetto `MathService` e quindi del progetto `MathService.Tests`. Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo, che viene superato.

## <a name="completing-the-requirements"></a>Completamento dei requisiti

Ora che il test è stato superato, è necessario scriverne altri. Il prossimo test case semplice opera su una sequenza in cui l'unico numero dispari è `1`. Il numero 1 è più semplice perché il quadrato di 1 è 1. Ecco questo test:

```fsharp
[<TestMethod>]
member public this.SumOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.sumOfSquares [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

Il nuovo test non viene superato con l'esecuzione di `dotnet test`. È necessario aggiornare il metodo `sumOfSquares` per gestire il nuovo test. È necessario filtrare tutti i numeri pari fuori sequenza per fare in modo che il test venga superato. È possibile farlo scrivendo una breve funzione di filtro e usando `Seq.filter`:

```fsharp
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

Si noti la chiamata a `Seq.toList`, che crea un elenco che implementa l'interfaccia <xref:System.Collections.ICollection>.

Manca un altro passaggio: elevare al quadrato ciascuno dei numeri di dispari. Per iniziare, scrivere un nuovo test:

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.sumOfSquares [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

È possibile correggere il test tramite il piping della sequenza filtrata attraverso un'operazione di mapping per calcolare il quadrato di ogni numero dispari:

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

È stata compilata una piccola libreria e un set di unit test per tale libreria. La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro. La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.
