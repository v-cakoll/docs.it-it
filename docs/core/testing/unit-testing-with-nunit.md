---
title: Testing unità di C# con NUnit e .NET Core
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e NUnit.
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 1ea17d9f830d8ac20e2bad79eebab5db767e0af8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714224"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>Testing unità di C# con NUnit e .NET Core

In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità. Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) prima di iniziare. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a>Prerequisiti

- [.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) o versioni successive.
- Editor di testo o editor di codice a scelta.

## <a name="creating-the-source-project"></a>Creazione del progetto di origine

Aprire una finestra della shell. Creare una directory denominata *unit-testing-using-nunit* in cui archiviare la soluzione. In questa nuova directory eseguire il comando seguente per creare un nuovo file di soluzione per la libreria di classi e il progetto di test:

```dotnetcli
dotnet new sln
```
 
Creare quindi una directory *PrimeService*. Finora è stata creata la struttura di directory e file seguente:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

Impostare *PrimeService* come directory corrente ed eseguire il comando seguente per creare il progetto di origine:

```dotnetcli
dotnet new classlib
```

Assegnare il nome *PrimeService.cs* al file *Class1.cs*. Si crea un'implementazione non corretta della classe `PrimeService`:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

Tornare alla directory *unit-testing-using-nunit*. Eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:

```dotnetcli
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a>Creazione del progetto di test

Creare quindi la directory *PrimeService.Tests*. Di seguito è illustrata la struttura di directory:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando il comando seguente:

```dotnetcli
dotnet new nunit
```

Il comando [dotnet new](../tools/dotnet-new.md) crea un progetto di test che usa NUnit come libreria di test. Il modello generato configura il Test Runner nel file *PrimeService.Tests.csproj*:

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti. `dotnet new` nel passaggio precedente aggiunge Microsoft Test SDK, il framework di test NUnit e l'adattatore di test NUnit. Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto. Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.

Il layout della soluzione finale è il seguente:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

Eseguire il comando seguente nella directory *unit-testing-using-nunit*:

```dotnetcli
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a>Creazione del primo test

Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo. Nella directory *PrimeService.Tests* rinominare il file *UnitTest1.cs* in *PrimeService_IsPrimeShould.cs* e sostituire l'intero contenuto con il codice seguente:

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        [Test]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            PrimeService primeService = CreatePrimeService();
            var result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
        
        /*
        More tests
        */
        
        private PrimeService CreatePrimeService()
        {
             return new PrimeService();
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
    throw new NotImplementedException("Please create a test first.");
}
```

Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-nunit*. Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`. Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo, che viene superato.

## <a name="adding-more-features"></a>Aggiunta di altre funzionalità

Ora che il test è stato superato, è necessario scriverne altri. Esistono alcuni altri casi semplici per i numeri primi: 0, -1. È possibile aggiungere nuovi test con l'attributo `[Test]`, ma questa operazione risulta rapidamente noiosa. Sono disponibili altri attributi NUnit che consentono di scrivere una suite di test analoghi.  Un attributo `[TestCase]` viene usato per creare una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi. È possibile usare l'attributo `[TestCase]` per specificare i valori per tali input.

Anziché creare nuovi test, applicare questo attributo per creare un singolo test basato sui dati. Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Eseguire `dotnet test`. Due test hanno esito negativo. Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo `Main` nel file *PrimeService.cs*:

```csharp
if (candidate < 2)
```

Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale. Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).

È stata compilata una piccola libreria e un set di unit test per tale libreria. La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro. La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.
