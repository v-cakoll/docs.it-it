---
title: Organizzazione e test di progetti con l'interfaccia della riga di comando di .NET Core
description: Questa esercitazione illustra come organizzare e testare i progetti .NET Core dalla riga di comando.
author: cartermp
ms.date: 09/10/2018
ms.openlocfilehash: 0d61e0fc004cfcb6d78c49475c7b7f0f523aad2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239911"
---
# <a name="organizing-and-testing-projects-with-the-net-core-cli"></a>Organizzazione e test di progetti con l'interfaccia della riga di comando di .NET Core

Questa esercitazione segue [Introduzione all'uso di .NET Core su Windows/Linux/macOS dalla riga di comando](cli-create-console-app.md) e va oltre la creazione di una semplice app console, illustrando lo sviluppo di applicazioni più avanzate e organizzate. L'esercitazione indica come usare le cartelle per organizzare il codice, quindi illustra come estendere un'applicazione console con il framework di testo [xUnit](https://xunit.github.io/).

## <a name="using-folders-to-organize-code"></a>Uso di cartelle per organizzare il codice

È possibile introdurre nuovi tipi in un'app console aggiungendo all'app i file contenenti i tipi. Se ad esempio si aggiungono al progetto file contenenti i tipi `AccountInformation` e `MonthlyReportRecords`, la struttura del progetto resta semplice e facile da esplorare:

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

Tuttavia questa soluzione funziona solo quando le dimensioni del progetto sono relativamente piccole. Si supponga di aggiungere 20 tipi al progetto. La navigazione e la manutenzione diventano più complicate per la presenza di molti file nella directory radice del progetto.

Per organizzare il progetto, creare una nuova cartella per l'archiviazione dei file dei tipi e denominarla *Models*. Inserire i file dei tipi nella cartella *Models*:

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

La navigazione e la manutenzione risultano più facili nei progetti che raggruppano i file in cartelle mediante codice. Nella sezione successiva viene creato un esempio più complesso con cartelle e unit test.

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a>Organizzare ed eseguire test con l'esempio NewTypes Pets

### <a name="building-the-sample"></a>Compilare l'esempio

Nelle fasi successive è possibile seguire [il progetto di esempio NewTypes Pets](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) o creare file e cartelle personalizzati. I tipi sono organizzati mediante codice in una struttura di cartelle che consente l'aggiunta di più tipi in un secondo momento. A loro volta i test sono inseriti mediante codice in cartelle che consentono l'aggiunta di altri test in un secondo momento.

L'esempio contiene due tipi `Dog` e `Cat` e definisce l'implementazione dell'interfaccia comune `IPet`. Per il progetto `NewTypes` l'obiettivo è l'organizzazione dei tipi associati agli animali domestici in una cartella *Pets*. Se in seguito viene aggiunto un altro set di tipi, ad esempio *WildAnimals*, questi vengono inseriti nella cartella *NewTypes* allo stesso livello della cartella *Pets*. La cartella *WildAnimals* può contenere tipi corrispondenti ad animali non domestici, ad esempio i tipi `Squirrel` e `Rabbit`. In questo modo mano a mano che vengono aggiunti dei tipi il progetto mantiene un'organizzazione ottimale.

Creare la seguente struttura di cartelle con il contenuto di file indicato:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

*IPet.cs*:

[!code-csharp[IPet interface](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/IPet.cs)]

*Dog.cs*:

[!code-csharp[Dog class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Dog.cs)]

*Cat.cs*:

[!code-csharp[Cat class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Cat.cs)]

*Program.cs*:

[!code-csharp[Main](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Program.cs)]

*NewTypes.csproj*:

[!code-xml[NewTypes csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/NewTypes.csproj)]

Eseguire il comando seguente:

```dotnetcli
dotnet run
```

L'output è il seguente:

```console
Woof!
Meow!
```

Esercizio facoltativo: aggiungere un nuovo tipo di animale domestico, ad esempio `Bird`, estendendo il progetto. Fare in modo che il metodo `TalkToOwner` corrispondente all'uccellino restituisca `Tweet!` al proprietario. Eseguire nuovamente l'app. L'output includerà `Tweet!`.

### <a name="testing-the-sample"></a>Test dell'esempio

Il progetto `NewTypes` è attivo ed è stato organizzato inserendo i tipi associati agli animali da compagnia in una cartella. Creare il progetto di test e iniziare a creare test con il framework di test [xUnit](https://xunit.github.io/). Il testing unità permette di controllare automaticamente il comportamento dei tipi di animali domestici per verificare che funzionino correttamente.

Tornare alla cartella *src* e creare una cartella *test* contenente una sottocartella *NewTypesTests*. Al prompt dei comandi della cartella *NewTypesTests* eseguire `dotnet new xunit`. Questa operazione produce due file: *NewTypesTests.csproj* e *UnitTest1.cs*.

Il progetto di test non può verificare i tipi in `NewTypes` e richiede un riferimento al progetto `NewTypes`. Per aggiungere un riferimento [`dotnet add reference`](../tools/dotnet-add-reference.md) al progetto, utilizzare il comando:To add a project reference, use the command:

```dotnetcli
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

In alternativa è possibile aggiungere manualmente il riferimento al progetto aggiungendo un nodo `<ItemGroup>` al file *NewTypesTests.csproj*:

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

*NewTypesTests.csproj*:

[!code-xml[NewTypesTests csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/NewTypesTests.csproj)]

Il file *NewTypesTests.csproj* contiene quanto segue:

* Riferimento pacchetto a `Microsoft.NET.Test.Sdk`, l'infrastruttura di test .NET
* Riferimento pacchetto a `xunit`, l'infrastruttura di test xUnit
* Riferimento pacchetto a `xunit.runner.visualstudio`, il Test Runner
* Riferimento progetto a `NewTypes`, il codice da sottoporre ai test

Cambiare il nome *UnitTest1.cs* in *PetTests.cs* e sostituire il codice del file con il codice seguente:

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }

    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }
}
```

Esercizio facoltativo: se in precedenza è stato aggiunto un tipo `Bird` che restituisce `Tweet!` al proprietario, aggiungere al file *PetTests.cs* un metodo di test `BirdTalkToOwnerReturnsTweet` per verificare che il metodo `TalkToOwner` funzioni correttamente per il tipo `Bird`.

> [!NOTE]
> Anche se si prevede che i valori `expected` e `actual` siano uguali, un'asserzione iniziale con le verifiche `Assert.NotEqual` specifica che questi valori sono *not equal* (diversi). Per verificare la logica del test, inizialmente creare sempre i test in modo che diano esito negativo. Dopo aver confermato che il test non riesce, modificare l'asserzione per fare in modo che il test venga superato.

Di seguito viene riportata la struttura completa del progetto:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

Iniziare nella directory *test/NewTypesTests*. Ripristinare il progetto [`dotnet restore`](../tools/dotnet-restore.md) di test con il comando. Eseguire i test [`dotnet test`](../tools/dotnet-test.md) con il comando . Questo comando avvia il Test Runner specificato nel file di progetto.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Come previsto, i test hanno esito negativo e la console visualizza il seguente output:

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.77]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:00.78]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 1.7000 Seconds
```

Modificare le asserzioni dei test da `Assert.NotEqual` a `Assert.Equal`:

[!code-csharp[PetTests class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/PetTests.cs)]

Eseguire nuovamente i test con il comando `dotnet test`. Si ottiene il seguente output:

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6029 Seconds
```

I test hanno esito positivo. I metodi dei tipi di animali da compagnia restituiscono i valori corretti nei messaggi trasmessi al proprietario.

Si sono apprese tecniche per l'organizzazione e il test di progetti con xUnit. Continuare con queste tecniche applicandole nei propri progetti. *Buon lavoro.*
