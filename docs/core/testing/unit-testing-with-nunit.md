---
title: "Testing unità di C# con NUnit e .NET Core"
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e NUnit.
keywords: NUnit, .NET, .NET Core
author: rprouse
ms.date: 12/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.openlocfilehash: ad410497adc641e89bd9845ed69c063692ad2f73
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>Testing unità di C# con NUnit e .NET Core

In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità. Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/) prima di iniziare. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Creazione del progetto di origine

Aprire una finestra della shell. Creare una directory denominata *unit-testing-using-nunit* in cui archiviare la soluzione. In questa nuova directory, eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare un nuovo file di soluzione per la libreria di classi e il progetto di test. Creare quindi una directory *PrimeService*. Finora è stata creata la struttura di directory e file seguente:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib`](../tools/dotnet-new.md) per creare il progetto di origine. Assegnare il nome *PrimeService.cs* al file *Class1.cs*. Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:

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

Tornare alla directory *unit-testing-using-nunit*. Eseguire [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.

## <a name="install-the-nunit-project-template"></a>Installare il modello di progetto NUnit

È necessario installare i modelli di progetto di test NUnit prima di creare un progetto di test. Questa operazione deve essere eseguita una sola volta in ogni computer di sviluppo in cui verranno creati nuovi progetti NUnit. Eseguire [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) per installare i modelli NUnit.

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a>Creazione del progetto di test

Creare quindi la directory *PrimeService.Tests*. Di seguito è illustrata la struttura di directory:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new nunit`](../tools/dotnet-new.md). Il comando dotnet new crea un progetto di test che usa NUnit come libreria di test. Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti. `dotnet new` nel passaggio precedente aggiunge Microsoft Test SDK, il framework di test NUnit e l'adattatore di test NUnit. Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto. Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.

Il layout della soluzione finale è il seguente:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) nella directory *unit-testing-using-dotnet-test*.

## <a name="creating-the-first-test"></a>Creazione del primo test

L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto. Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C# denominato *PrimeService_IsPrimeShould.cs* con il contenuto seguente:

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

L'attributo `[TestFixture]` indica una classe che contiene unit test. L'attributo `[Test]` indica che il metodo è un metodo di test.

Salvare questo file ed eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test. Il Test Runner di NUnit include il punto d'ingresso del programma per l'esecuzione dei test. `dotnet test` avvia il Test Runner usando il progetto di unit test creato.

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

Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-nunit*. Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`. Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo, che viene superato.

## <a name="adding-more-features"></a>Aggiunta di altre funzionalità

Ora che il test è stato superato, è necessario scriverne altri. Esistono alcuni altri casi semplici per i numeri primi: 0, -1. È possibile aggiungere nuovi test con l'attributo `[Test]`, ma questa operazione risulta rapidamente noiosa. Sono disponibili altri attributi NUnit che consentono di scrivere una suite di test analoghi.  Un attributo `[TestCase]` viene usato per creare una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi. È possibile usare l'attributo `[TestCase]` per specificare i valori per tali input.

Anziché creare nuovi test, applicare questo attributo per creare un singolo test basato sui dati. Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Eseguire `dotnet test`. Due test hanno esito negativo. Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:

```csharp
if (candidate < 2)
```

Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale. Si ottiene la [versione completa dei test](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).

È stata compilata una piccola libreria e un set di unit test per tale libreria. La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro. La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.
