---
title: "Testing unità con Visual Basic in .NET Core usando il test dotnet e NUnit"
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di Visual Basic di esempio con NUnit.
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs:
- vb
ms.prod: .net-core
ms.openlocfilehash: 2166da36fe9d0297f03e7c38249135d281b9a5d6
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a>Testing unità di librerie .NET Core di Visual Basic usando il test dotnet e NUnit

In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità. Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-vb-nunit/) prima di iniziare. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Creazione del progetto di origine

Aprire una finestra della shell. Creare una directory denominata *unit-testing-vb-nunit* in cui archiviare la soluzione. In questa nuova directory eseguire [`dotnet new sln`](../tools/dotnet-new.md) per creare una nuova soluzione. Questa procedura semplifica la gestione sia della libreria di classi che del progetto di unit test. All'interno della directory della soluzione creare una directory *PrimeService*. Finora è stata creata la struttura di directory e file seguente:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) per creare il progetto di origine. Rinominare *Class1.VB* in *PrimeService.VB*. Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione non corretta della classe `PrimeService`:

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

Tornare alla directory *unit-testing-vb-using-stest*. Eseguire [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) per aggiungere il progetto di libreria di classi alla soluzione.

## <a name="install-the-nunit-project-template"></a>Installare il modello di progetto NUnit

È necessario installare i modelli di progetto di test NUnit prima di creare un progetto di test. Questa operazione deve essere eseguita una sola volta in ogni computer di sviluppo in cui verranno creati nuovi progetti NUnit. Eseguire [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) per installare i modelli NUnit.

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a>Creazione del progetto di test

Creare quindi la directory *PrimeService.Tests*. Di seguito è illustrata la struttura di directory:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new nunit -lang VB`](../tools/dotnet-new.md). Questo comando crea un progetto di test che usa NUnit come libreria di test. Il modello generato configura il Test Runner nel file *PrimeServiceTests.vbproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti. `dotnet new` nel passaggio precedente aggiunge NUnit e l'adattatore di test NUnit. Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto. Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) su GitHub.

Il layout della soluzione finale è il seguente:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

Eseguire [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) nella directory *unit-testing-vb-nunit*.

## <a name="creating-the-first-test"></a>Creazione del primo test

L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto. Rimuovere *UnitTest1.vb* dalla directory *PrimeService.Tests* e creare un nuovo file di Visual Basic denominato *PrimeService_IsPrimeShould.VB*. Aggiungere il codice seguente:

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

L'attributo `<TestFixture>` indica una classe che contiene test. L'attributo `<Test>` indica un metodo eseguito dal Test Runner. Da *unit-testing-vb-nunit* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test. Il Test Runner di NUnit include il punto d'ingresso del programma per l'esecuzione dei test. `dotnet test` avvia il Test Runner usando il progetto di unit test creato.

Il test ha esito negativo. Non è stata ancora creata l'implementazione. Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `PrimeService`:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

Eseguire di nuovo `dotnet test` nella directory *unit-testing-vb-nunit*. Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`. Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo, che viene superato.

## <a name="adding-more-features"></a>Aggiunta di altre funzionalità

Ora che il test è stato superato, è necessario scriverne altri. Esistono alcuni altri casi semplici per i numeri primi: 0, -1. È possibile aggiungerli come nuovi test, con l'attributo `<Test>`, ma questa operazione risulta rapidamente noiosa. Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi.  Un attributo `<TestCase>` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi. È possibile usare l'attributo `<TestCase>` per specificare i valori per tali input.

Anziché creare nuovi test, applicare questi due attributi per creare una serie di test che verificano diversi valori minori di due, ovvero il numero primo più basso:

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Eseguire `dotnet test`. Due test hanno esito negativo. Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:

```vb
if candidate < 2
```

Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale. Si ottiene la [versione completa dei test](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) e l'[implementazione completa della libreria](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).

È stata compilata una piccola libreria e un set di unit test per tale libreria. La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro. La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.
