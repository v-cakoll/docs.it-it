---
title: Testing unità di codice C# in .NET Core usando il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: c9e3d63a2cf4f560591459833340b729ffec1b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240896"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Testing unità di C# in .NET Core usando il test dotnet e xUnit

Questa esercitazione illustra come compilare una soluzione contenente un progetto di unit test e un progetto di codice sorgente. Per seguire l'esercitazione utilizzando una soluzione predefinita, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/). Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="create-the-solution"></a>Creare la soluzione

In questa sezione viene creata una soluzione che contiene i progetti di origine e test. La soluzione completata ha la seguente struttura di directory:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.cs
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.cs
        PrimeServiceTests.csproj
```

Le istruzioni seguenti illustrano i passaggi per creare la soluzione di test. Vedere [Comandi per creare](#create-test-cmd) una soluzione di test per istruzioni su come creare la soluzione di test in un unico passaggio.

* Aprire una finestra della shell.
* Eseguire il comando seguente:

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  Il [`dotnet new sln`](../tools/dotnet-new.md) comando crea una nuova soluzione nella directory *unit-testing-using-dotnet-test.*
* Passare alla directory *unit-testing-using-dotnet-test.*
* Eseguire il comando seguente:

  ```dotnetcli
  dotnet new classlib -o PrimeService
  ```

   Il [`dotnet new classlib`](../tools/dotnet-new.md) comando crea un nuovo progetto libreria di classi nella cartella *PrimeService.The* command creates a new class library project in the PrimeService folder. La nuova libreria di classi conterrà il codice da testare.
* Assegnare il nome *PrimeService.cs* al file *Class1.cs*.
* Sostituire il codice in *PrimeService.cs* con il codice seguente:
  
  ```csharp
    using System;

    namespace Prime.Services
    {
        public class PrimeService
        {
            public bool IsPrime(int candidate)
            {
                throw new NotImplementedException("Not implemented.");
            }
        }
    }
  ```

* Il codice precedente:
  * Genera un <xref:System.NotImplementedException> con un messaggio che indica che non è implementato.
  * Viene aggiornato più avanti nell'esercitazione.

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* Nella directory *unit-testing-using-dotnet-test* eseguire il comando seguente per aggiungere il progetto della libreria di classi alla soluzione:

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.csproj
  ```

* Creare il progetto *PrimeService.Tests* eseguendo il comando seguente:

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* Il comando precedente:
  * Crea il progetto *PrimeService.Tests* nella directory *PrimeService.Tests.* Il progetto di test utilizza [xUnit](https://xunit.github.io/) come libreria di test.
  * Configura il test runner aggiungendo `<PackageReference />`i seguenti elementi al file di progetto:
    * "Microsoft.NET.Test.Sdk"
    * "xunità"
    * "xunit.runner.visualstudio"

* Aggiungere il progetto di test al file di soluzione eseguendo il comando seguente:

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
  ```

* Aggiungere `PrimeService` la libreria di classi come dipendenza al progetto *PrimeService.Tests:Add* the class library as a dependency to the PrimeService.Tests project:

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>Comandi per creare la soluzione

In questa sezione vengono riepilogati tutti i comandi della sezione precedente. Ignorare questa sezione se sono stati completati i passaggi della sezione precedente.

I comandi seguenti creano la soluzione di test in un computer Windows.The following commands create the test solution on a windows machine. Per macOS e Unix, aggiornare il `ren` `ren` comando alla versione del sistema operativo di per rinominare un file:

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.cs PrimeService.cs
dotnet sln add ./PrimeService/PrimeService.csproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

Seguire le istruzioni per "Sostituire il codice in *PrimeService.cs* con il codice seguente" nella sezione precedente.

## <a name="create-a-test"></a>Creare un testCreate a test

Un approccio comune nello sviluppo basato su test (TDD) consiste nello scrivere un test prima di implementare il codice di destinazione. Questa esercitazione usa l'approccio TDD. Il `IsPrime` metodo è richiamabile, ma non implementato. Una chiamata `IsPrime` di prova a ha esito negativo. Con TDD, viene scritto un test che è noto per non riuscire. Il codice di destinazione viene aggiornato per eseguire il test. Continuare a ripetere questo approccio, scrivere un test non superato e quindi aggiornare il codice di destinazione per passare.

Aggiornare il progetto *PrimeService.Tests:*

* Eliminare *PrimeService.Tests/UnitTest1.cs*.
* Creare un file *PrimeService.Tests/PrimeService_IsPrimeShould.cs.Create a PrimeService.Tests/PrimeService_IsPrimeShould.cs* file.
* Sostituire il codice in *PrimeService_IsPrimeShould.cs* con il codice seguente:

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
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

L'attributo `[Fact]` dichiara un metodo di test eseguito dal test runner. Dalla cartella *PrimeService.Tests* `dotnet test`eseguire . Il comando [dotnet test](../tools/dotnet-test.md) compila entrambi i progetti ed esegue i test. Il test runner xUnit contiene il punto di ingresso del programma per eseguire i test. `dotnet test`avvia il test runner utilizzando il progetto di unit test.

Il test `IsPrime` ha esito negativo perché non è stato implementato. Utilizzando l'approccio TDD, scrivere solo codice sufficiente in modo che questo test viene superato. Aggiornare con il codice seguente:Update `IsPrime` with the following code:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

Eseguire `dotnet test`. Il test viene superato.

### <a name="add-more-tests"></a>Aggiungere altri test

Aggiungere i test dei numeri primi per 0 e -1. È possibile copiare il test precedente e modificare il codice seguente per usare 0 e -1:

```csharp
var result = _primeService.IsPrime(1);

Assert.False(result, "1 should not be prime");
```

La copia del codice di test quando solo un parametro viene modificato comporta la duplicazione del codice e il test del problema. I seguenti attributi xUnit consentono la scrittura di un gruppo di test simili:

- `[Theory]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.

- L'attributo `[InlineData]` specifica i valori per tali input.

Anziché creare nuovi test, applicare gli attributi xUnit precedenti per creare una singola teoria. Sostituire il codice seguente:

```csharp
[Fact]
public void IsPrime_InputIs1_ReturnFalse()
{
    var result = _primeService.IsPrime(1);

    Assert.False(result, "1 should not be prime");
}
```

con il codice seguente:

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-dotnet-test/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Nel codice precedente `[Theory]` e `[InlineData]` abilitare il test di diversi valori minori di due. Due è il numero primo più piccolo.

Eseguire `dotnet test`, due dei test hanno esito negativo. Per eseguire tutti i test, `IsPrime` aggiornare il metodo con il codice seguente:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate < 2)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

Seguendo l'approccio TDD, aggiungere altri test non superati, quindi aggiornare il codice di destinazione. Vedere la [versione completata dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'implementazione completa della [libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

Il `IsPrime` metodo completato non è un algoritmo efficiente per testare la primalità.

### <a name="additional-resources"></a>Risorse aggiuntive

- [Sito ufficiale xUnit.net](https://xunit.github.io)
- [Test della logica dei controller in ASP.NET Core](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
