---
title: Testing unità di codice C# in .NET Core usando il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 226db54047747fbd065c64f5e4812094921c7f62
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714242"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Testing unità di C# in .NET Core usando il test dotnet e xUnit

Questa esercitazione illustra come compilare una soluzione contenente un progetto unit test e un progetto di codice sorgente. Per seguire l'esercitazione usando una soluzione predefinita, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/). Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="create-the-solution"></a>Creare la soluzione

In questa sezione viene creata una soluzione che contiene i progetti di origine e di test. La soluzione completa presenta la struttura di directory seguente:

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

Le istruzioni seguenti forniscono i passaggi per creare la soluzione di test. Per istruzioni su come creare la soluzione di test in un unico passaggio, vedere [comandi per creare una soluzione di test](#create-test-cmd) .

* Aprire una finestra della shell.
* Eseguire il comando seguente:

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  Il comando [`dotnet new sln`](../tools/dotnet-new.md) crea una nuova soluzione nella directory *unit-testing-using-DotNet-test* .
* Passare alla cartella *unit-testing-using-DotNet-test* .
* Eseguire il comando seguente:

  ```dotnetcli
  dotnet new classlib -o PrimeService
  ```

   Il [`dotnet new classlib`](../tools/dotnet-new.md) comando crea un nuovo progetto di libreria di classi nella cartella *PrimeService* . La nuova libreria di classi conterrà il codice da testare.
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

* Nella directory *unit-testing-using-DotNet-test* eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.csproj
  ```

* Creare il progetto *PrimeService. tests* eseguendo il comando seguente:

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* Il comando precedente:
  * Crea il progetto *PrimeService. tests* nella directory *PrimeService. tests* . Il progetto di test USA [xUnit](https://xunit.github.io/) come libreria di test.
  * Configura il test runner aggiungendo gli elementi `<PackageReference />`seguenti al file di progetto:
    * "Microsoft. NET. test. SDK"
    * xUnit
    * "xUnit. Runner. VisualStudio"

* Aggiungere il progetto di test al file di soluzione eseguendo il comando seguente:

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
  ```

* Aggiungere la libreria di classi `PrimeService` come dipendenza al progetto *PrimeService. tests* :

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>Comandi per creare la soluzione

In questa sezione vengono riepilogati tutti i comandi della sezione precedente. Ignorare questa sezione se è stata completata la procedura descritta nella sezione precedente.

I comandi seguenti creano la soluzione di test in un computer Windows. Per macOS e UNIX, aggiornare il comando `ren` alla versione del sistema operativo di `ren` per rinominare un file:

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

Seguire le istruzioni per "sostituire il codice in *PrimeService.cs* con il codice seguente" nella sezione precedente.

## <a name="create-a-test"></a>Creare un test

Un approccio comune nello sviluppo basato su test (TDD) consiste nel scrivere un test prima di implementare il codice di destinazione. Questa esercitazione usa l'approccio TDD. Il metodo `IsPrime` è chiamabile, ma non è implementato. Una chiamata di test a `IsPrime` ha esito negativo. Con TDD, viene scritto un test noto come non riuscito. Il codice di destinazione viene aggiornato per fare in modo che il test venga superato. Si continua a ripetere questo approccio, scrivendo un test con esito negativo e quindi aggiornando il codice di destinazione da passare.

Aggiornare il progetto *PrimeService. tests* :

* Eliminare *PrimeService. tests/UnitTest1. cs*.
* Creare un file *PrimeService. tests/PrimeService_IsPrimeShould. cs* .
* Sostituire il codice in *PrimeService_IsPrimeShould. cs* con il codice seguente:

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

L'attributo `[Fact]` dichiara un metodo di test eseguito dal test runner. Dalla cartella *PrimeService. tests* eseguire `dotnet test`. Il comando [DotNet test](../tools/dotnet-test.md) Compila entrambi i progetti ed esegue i test. XUnit Test Runner contiene il punto di ingresso del programma per eseguire i test. `dotnet test` avvia il test runner utilizzando il progetto unit test.

Il test ha esito negativo perché `IsPrime` non è stato implementato. Utilizzando l'approccio TDD, scrivere solo codice sufficiente per consentire il superamento del test. Aggiornare `IsPrime` con il codice seguente:

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

Eseguire `dotnet test`. Il test ha esito positivo.

### <a name="add-more-tests"></a>Aggiungi altri test

Aggiungere i test dei numeri primi per 0 e-1. È possibile copiare il test precedente e modificare il codice seguente per usare 0 e-1:

```csharp
var result = _primeService.IsPrime(1);

Assert.False(result, "1 should not be prime");
```

La copia del codice di test quando solo un parametro cambia causa la duplicazione del codice e il sovraccarico dei test. Gli attributi xUnit seguenti consentono di scrivere una suite di test simili:

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

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Nel codice precedente `[Theory]` e `[InlineData]` abilitano il testing di diversi valori minori di due. Due è il numero primo più piccolo.

Eseguire `dotnet test`, due dei test hanno esito negativo. Per far passare tutti i test, aggiornare il metodo `IsPrime` con il codice seguente:

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

Seguendo l'approccio di TDD, aggiungere altri test non superati, quindi aggiornare il codice di destinazione. Vedere la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l' [implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

Il metodo di `IsPrime` completato non è un algoritmo efficiente per il test di primalità.

### <a name="additional-resources"></a>Risorse aggiuntive

- [Sito ufficiale xUnit.net](https://xunit.github.io)
- [Test della logica dei controller in ASP.NET Core](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
