---
title: "Testing unità di codice C# in .NET Core usando il test dotnet e xUnit"
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 6e986e89d47ba4de9b8563f1a95cb1ae89accc89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Testing unità di C# in .NET Core usando il test dotnet e xUnit

In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità. Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) prima di iniziare. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Creazione del progetto di origine

Aprire una finestra della shell. Creare una directory denominata *unit-testing-using-dotnet-test* in cui archiviare la soluzione.
In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione. Questo rende più semplice gestire sia la libreria di classi che il progetto di unit test.
All'interno della directory della soluzione creare una directory *PrimeService*. La struttura della directory e dei file fino a questo momento è la seguente:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib`](../tools/dotnet-new.md) per creare il progetto di origine. Assegnare il nome *PrimeService.cs* al file *Class1.cs*. Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione con esito negativo della classe `PrimeService`:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

Tornare alla directory *unit-testing-using-dotnet-test*. Eseguire [`dotnet sln add .\PrimeService\PrimeService.csproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.

## <a name="creating-the-test-project"></a>Creazione del progetto di test

Creare quindi la directory *PrimeService.Tests*. Di seguito è illustrata la struttura di directory:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new xunit`](../tools/dotnet-new.md). In questo modo viene creato un progetto di test che usa xUnit come libreria di test. Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti. Nel passaggio precedente `dotnet new` ha aggiunto xUnit e il Runner di xUnit. Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto. Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.

Il layout della soluzione finale è il seguente:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) nella directory *unit-testing-using-dotnet-test*. 

## <a name="creating-the-first-test"></a>Creazione del primo test

L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto. Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C# denominato *PrimeService_IsPrimeShould.cs*. Aggiungere il codice seguente:

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

L'attributo `[Fact]` indica un metodo di test eseguito dal Test Runner. Da *unit-testing-using-dotnet-test* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test. Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test. `dotnet test` avvia il Test Runner usando il progetto di unit test creato.

Il test ha esito negativo. Non è stata ancora creata l'implementazione. Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-dotnet-test*. Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`. Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo, che viene superato.

## <a name="adding-more-features"></a>Aggiunta di altre funzionalità

Ora che il test è stato superato, è necessario scriverne altri. Esistono alcuni altri casi semplici per i numeri primi: 0, -1. È possibile aggiungerli come nuovi test, con l'attributo `[Fact]`, ma questa operazione risulta rapidamente noiosa. Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi.  Un attributo `[Theory]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi. È possibile usare l'attributo `[InlineData]` per specificare i valori per tali input.

Anziché creare nuovi test, applicare questi due attributi per creare una singola teoria. La teoria è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Eseguire `dotnet test`. Due test hanno esito negativo. Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:

```csharp
if (candidate < 2)
```

Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale. Si ottiene la [versione completa dei test](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

### <a name="additional-resources"></a>Risorse aggiuntive

[Logica di controller di test in ASP.NET Core](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)
