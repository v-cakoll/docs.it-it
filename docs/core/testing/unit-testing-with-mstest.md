---
title: Testing unità di C# con MSTest e .NET Core
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e MSTest.
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.openlocfilehash: bd7891243d84277a7578089f8b4629ff5bada577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240909"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a>Testing unità di C# con MSTest e .NET Core

In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità. Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) prima di iniziare. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="create-the-source-project"></a>Creare il progetto di origine

Aprire una finestra della shell. Creare una directory denominata *unit-testing-using-mstest* in cui archiviare la soluzione. All'interno di [`dotnet new sln`](../tools/dotnet-new.md) questa nuova directory, eseguire per creare un nuovo file di soluzione per la libreria di classi e il progetto di test. Creare quindi una directory *PrimeService*. Finora è stata creata la struttura di directory e file seguente:

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

Impostare *PrimeService* come [`dotnet new classlib`](../tools/dotnet-new.md) directory corrente ed eseguire per creare il progetto di origine. Assegnare il nome *PrimeService.cs* al file *Class1.cs*. Si crea un'implementazione non corretta della classe `PrimeService`:

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

Tornare alla directory *unit-testing-using-mstest*. Esegui [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.

## <a name="create-the-test-project"></a>Creare il progetto di test

Creare quindi la directory *PrimeService.Tests*. Di seguito è illustrata la struttura di directory:

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Impostare la directory *PrimeService.Tests* come directory [`dotnet new mstest`](../tools/dotnet-new.md)corrente e creare un nuovo progetto utilizzando . Il comando dotnet new crea un progetto di test che usa MSTest come libreria di test. Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti. Nel passaggio precedente `dotnet new` ha aggiunto l'SDK MSTest, il framework di test MSTest e il Test Runner MSTest. Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto. Utilizzare [`dotnet add reference`](../tools/dotnet-add-reference.md) il comando:

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.

Il layout della soluzione finale è il seguente:

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) nella directory *unit-testing-using-mstest.*

## <a name="create-the-first-test"></a>Creare il primo test

Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo. Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C , denominato *PrimeService_IsPrimeShould.cs* con il contenuto seguente:

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

L'[attributo TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) indica una classe che contiene unit test. L'[attributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indica che il metodo è un metodo di test.

Salvare il file [`dotnet test`](../tools/dotnet-test.md) ed eseguire per compilare i test e la libreria di classi e quindi eseguire i test. Il Test Runner di MSTest include il punto d'ingresso del programma per l'esecuzione dei test. `dotnet test` avvia il Test Runner usando il progetto di unit test creato.

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

Eseguire di nuovo `dotnet test` nella directory *unit-testing-using-mstest*. Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`. Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo, che viene superato.

## <a name="add-more-features"></a>Aggiungere altre funzionalità

Ora che il test è stato superato, è necessario scriverne altri. Esistono alcuni altri casi semplici per i numeri primi: 0, -1. È possibile aggiungere nuovi test con l'[attributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), ma questa operazione risulta rapidamente noiosa. Sono disponibili altri attributi di MSTest che consentono di scrivere una suite di test analoghi.  Un [attributo DataTestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi. È possibile usare l'[attributo DataRow](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) per specificare i valori per tali input.

Anziché creare nuovi test, applicare questi due attributi per creare un singolo test basato sui dati. Il test basato sui dati è un metodo che verifica vari valori minori di due, ovvero il numero primo più piccolo:

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-mstest/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Eseguire `dotnet test`. Due test hanno esito negativo. Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:

```csharp
if (candidate < 2)
```

Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale. Si ottiene la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).

È stata compilata una piccola libreria e un set di unit test per tale libreria. La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro. La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [Usare il framework MSTest negli unit test](/visualstudio/test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests)
- [Documentazione del framework di test MSTest V2](https://github.com/Microsoft/testfx-docs)
