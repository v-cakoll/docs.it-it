---
title: Testing unità di Visual Basic in .NET Core con il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di Visual Basic di esempio con test dotnet e xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 05/18/2020
ms.openlocfilehash: ed1291a980f9a39284525877bab8d0a93389fbd0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702954"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a>Testing unità di librerie .NET Core di Visual Basic usando il test dotnet e xUnit

Questa esercitazione illustra come compilare una soluzione contenente un progetto unit test e un progetto di libreria. Per seguire l'esercitazione usando una soluzione predefinita, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/). Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="create-the-solution"></a>Creare la soluzione

In questa sezione viene creata una soluzione che contiene i progetti di origine e di test. La soluzione completa presenta la struttura di directory seguente:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.vb
        PrimeService.vbproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.vb
        PrimeServiceTests.vbproj
```

Le istruzioni seguenti forniscono i passaggi per creare la soluzione di test. Per istruzioni su come creare la soluzione di test in un unico passaggio, vedere [comandi per creare una soluzione di test](#create-test-cmd) .

* Aprire una finestra della shell.
* Eseguire il comando seguente:

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  Il [`dotnet new sln`](../tools/dotnet-new.md) comando crea una nuova soluzione nella directory *unit-testing-using-DotNet-test* .
* Passare alla cartella *unit-testing-using-DotNet-test* .
* Eseguire il comando seguente:

  ```dotnetcli
  dotnet new classlib -o PrimeService --lang VB
  ```

   Il [`dotnet new classlib`](../tools/dotnet-new.md) comando crea un nuovo progetto libreria di classi nella cartella *PrimeService* . La nuova libreria di classi conterrà il codice da testare.
* Rinominare *Class1. vb* in *PrimeService. vb*.
* Sostituire il codice in *PrimeService. vb* con il codice seguente:
  
  ```vb
  Imports System
  
  Namespace Prime.Services
      Public Class PrimeService
          Public Function IsPrime(candidate As Integer) As Boolean
              Throw New NotImplementedException("Not implemented.")
          End Function
      End Class
  End Namespace
  ```

* Il codice precedente:
  * Genera un'eccezione <xref:System.NotImplementedException> con un messaggio che indica che non è implementato.
  * Viene aggiornato più avanti nell'esercitazione.

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* Nella directory *unit-testing-using-DotNet-test* eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.vbproj
  ```

* Creare il progetto *PrimeService. tests* eseguendo il comando seguente:

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* Il comando precedente:
  * Crea il progetto *PrimeService. tests* nella directory *PrimeService. tests* . Il progetto di test USA [xUnit](https://xunit.net/) come libreria di test.
  * Configura il test runner aggiungendo gli `<PackageReference />` elementi seguenti al file di progetto:
    * "Microsoft. NET. test. SDK"
    * xUnit
    * "xUnit. Runner. VisualStudio"

* Aggiungere il progetto di test al file di soluzione eseguendo il comando seguente:

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
  ```

* Aggiungere la `PrimeService` libreria di classi come dipendenza al progetto *PrimeService. tests* :

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>Comandi per creare la soluzione

In questa sezione vengono riepilogati tutti i comandi della sezione precedente. Ignorare questa sezione se è stata completata la procedura descritta nella sezione precedente.

I comandi seguenti creano la soluzione di test in un computer Windows. Per macOS e UNIX, aggiornare il `ren` comando alla versione del sistema operativo di `ren` per rinominare un file:

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.vb PrimeService.vb
dotnet sln add ./PrimeService/PrimeService.vbproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
```

Seguire le istruzioni per "sostituire il codice in *PrimeService. vb* con il codice seguente" nella sezione precedente.

## <a name="create-a-test"></a>Creare un test

Un approccio comune nello sviluppo basato su test (TDD) consiste nel scrivere un test prima di implementare il codice di destinazione. Questa esercitazione usa l'approccio TDD. Il `IsPrime` metodo è chiamabile, ma non è implementato. Una chiamata di test a ha `IsPrime` esito negativo. Con TDD, viene scritto un test noto come non riuscito. Il codice di destinazione viene aggiornato per fare in modo che il test venga superato. Si continua a ripetere questo approccio, scrivendo un test con esito negativo e quindi aggiornando il codice di destinazione da passare.

Aggiornare il progetto *PrimeService. tests* :

* Eliminare *PrimeService. tests/UnitTest1. vb*.
* Creare un file *PrimeService. tests/PrimeService_IsPrimeShould. vb* .
* Sostituire il codice in *PrimeService_IsPrimeShould. vb* con il codice seguente:

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private ReadOnly _primeService As Prime.Services.PrimeService

        Public Sub New()
            _primeService = New Prime.Services.PrimeService()
        End Sub


        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

L' `[Fact]` attributo dichiara un metodo di test eseguito dal test runner. Dalla cartella *PrimeService. tests* eseguire `dotnet test` . Il comando [DotNet test](../tools/dotnet-test.md) Compila entrambi i progetti ed esegue i test. XUnit Test Runner contiene il punto di ingresso del programma per eseguire i test. `dotnet test`avvia il test runner utilizzando il progetto unit test.

Il test non riesce perché `IsPrime` non è stato implementato. Utilizzando l'approccio TDD, scrivere solo codice sufficiente per consentire il superamento del test. Aggiornare `IsPrime` con il codice seguente:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Not implemented.")
End Function
```

Eseguire `dotnet test`. Il test viene superato.

### <a name="add-more-tests"></a>Aggiungi altri test

Aggiungere i test dei numeri primi per 0 e-1. È possibile copiare il test precedente e modificare il codice seguente per usare 0 e-1:

```vb
Dim result As Boolean = _primeService.IsPrime(1)

Assert.False(result, "1 should not be prime")
```

La copia del codice di test quando solo un parametro cambia causa la duplicazione del codice e il sovraccarico dei test. Gli attributi xUnit seguenti consentono di scrivere una suite di test simili:

- `[Theory]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.
- L'attributo `[InlineData]` specifica i valori per tali input.

Anziché creare nuovi test, applicare gli attributi xUnit precedenti per creare una singola teoria. Sostituire il codice seguente:

```vb
<Fact>
Sub IsPrime_InputIs1_ReturnFalse()
    Dim result As Boolean = _primeService.IsPrime(1)

    Assert.False(result, "1 should not be prime")
End Sub
```

con il codice seguente:

```vb
<Theory>
<InlineData(-1)>
<InlineData(0)>
<InlineData(1)>
Sub IsPrime_ValuesLessThan2_ReturnFalse(ByVal value As Integer)
    Dim result As Boolean = _primeService.IsPrime(value)

    Assert.False(result, $"{value} should not be prime")
End Sub
```

Nel codice precedente, `[Theory]` e `[InlineData]` consentono di testare diversi valori minori di due. Due è il numero primo più piccolo.

Eseguire `dotnet test` , due dei test hanno esito negativo. Per far passare tutti i test, aggiornare il `IsPrime` metodo con il codice seguente:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate < 2 Then
        Return False
    End If
    Throw New NotImplementedException("Not fully implemented.")
End Function
```

Seguendo l'approccio di TDD, aggiungere altri test non superati, quindi aggiornare il codice di destinazione. Vedere la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) e l' [implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.vb).

Il `IsPrime` metodo Completed non è un algoritmo efficiente per il test di primalità.

### <a name="additional-resources"></a>Risorse aggiuntive

- [Sito ufficiale xUnit.net](https://xunit.net/)
- [Test della logica dei controller in ASP.NET Core](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
