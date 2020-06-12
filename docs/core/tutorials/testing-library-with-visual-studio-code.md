---
title: Testare una libreria di classi .NET Standard con .NET Core usando Visual Studio Code
description: Creare un progetto unit test per una libreria di classi .NET Core. Verificare che una libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 06/08/2020
ms.openlocfilehash: a61fd952eea2dec0d5a9f351d3f3d01c738e8fad
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701033"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio-code"></a>Esercitazione: testare una libreria di classi .NET Standard con .NET Core usando Visual Studio Code

Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio Code](library-with-visual-studio-code.md).

## <a name="create-a-unit-test-project"></a>Creare un progetto di unit test

Gli unit test forniscono test software automatici durante le fasi di sviluppo e pubblicazione. Il Framework di test usato in questa esercitazione è MSTest. [MSTest](https://github.com/Microsoft/testfx-docs) è uno dei tre Framework di test tra cui è possibile scegliere. Gli altri sono [xUnit](https://xunit.net/) e [NUnit](https://nunit.org/).

1. Avviare Visual Studio Code.

1. Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).

1. Creare un progetto unit test denominato "StringLibraryTest".

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   Il modello di progetto crea un file UnitTest1.cs con il codice seguente:

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

   namespace StringLibraryTest
   {
       [TestClass]
       public class UnitTest1
       {
           [TestMethod]
           public void TestMethod1()
           {
           }
       }
   }
   ```

   Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:

   - Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.
   - Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.
   - Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo da definire `TestMethod1` .

   Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.

1. Aggiungere il progetto di test alla soluzione.

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a>Aggiungere un riferimento al progetto

Per usare il progetto di test con la `StringLibrary` classe, aggiungere un riferimento al progetto nel progetto `StringLibraryTest` `StringLibrary` .

1. Eseguire il comando seguente:

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a>Aggiungere ed eseguire unit test metodi

Quando Visual Studio esegue una unit test, viene eseguito ogni metodo contrassegnato con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo in una classe contrassegnata con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attributo. Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.

I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo. `Assert`Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe:

| Metodi Assert     | Funzione |
| ------------------ | -------- |
| `Assert.AreEqual`  | Verifica che due oggetti o valori siano uguali. L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali. |
| `Assert.AreSame`   | Verifica che due variabili oggetto facciano riferimento allo stesso oggetto. Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi. |
| `Assert.IsFalse`   | Verifica che una condizione sia `false`. Il metodo ha esito negativo se la condizione è `true`. |
| `Assert.IsNotNull` | Verifica che un oggetto non sia `null` . Il metodo ha esito negativo se l'oggetto è `null`. |

È anche possibile usare il <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodo in un metodo di test per indicare il tipo di eccezione che si prevede venga generata. Il test ha esito negativo se l'eccezione specificata non viene generata.

Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>. Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo. In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.

Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty) e un oggetto e una `null` stringa. Una stringa vuota non contiene caratteri e il cui valore <xref:System.String.Length> è 0. Una `null` stringa è una stringa che non è stata inizializzata. È possibile chiamare `StartsWithUpper` direttamente come metodo statico e passare un singolo <xref:System.String> argomento. In alternativa, è possibile chiamare `StartsWithUpper` come metodo di estensione su una `string` variabile assegnata a `null` .

Verranno definiti tre metodi, ognuno dei quali chiama un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodo per ogni elemento in una matrice di stringhe. Si chiamerà un overload del metodo che consente di specificare un messaggio di errore da visualizzare in caso di errore del test. Il messaggio identifica la stringa che ha causato l'errore.

Per creare i metodi di test:

1. Aprire *StringLibraryTest/UnitTest1. cs* e sostituire tutto il codice con il codice seguente.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico. Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).

1. Salvare le modifiche.

1. Eseguire i test:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   L'output del terminale mostra che tutti i test sono stati superati.

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a>Gestione degli errori di test

Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti. Si aggiunge quindi il codice all'app che rende il test riuscito. Per questa esercitazione è stato creato il test dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito. Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.

1. Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error".

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. Eseguire i test:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   L'output del terminale mostra che un test ha esito negativo e fornisce un messaggio di errore per il test non superato: "Assert. false non riuscito. Expected for 'Error': false; actual: True". A causa dell'errore, non sono state testate stringhe nella matrice dopo l'errore.

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.
     X TestDoesNotStartWithUpper [283ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
     at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper()
       in C:\Projects\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Test Run Failed.
   Total tests: 3
        Passed: 2
        Failed: 1
   Total time: 1.7825 Seconds
   ```

1. Rimuovere la stringa "Error" aggiunta nel passaggio 1. Eseguire di nuovo il test e i test superati.

## <a name="test-the-release-version-of-the-library"></a>Testare la versione di rilascio della libreria

Ora che i test sono stati superati quando si esegue la build di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria. Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.

1. Eseguire i test con la configurazione della build di rilascio:

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   I test avranno esito positivo.

## <a name="additional-resources"></a>Risorse aggiuntive

* [Testing unità in .NET Core e .NET Standard](../testing/index.md)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata testata una libreria di classi. Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto. Per informazioni su come seguire un'esercitazione su NuGet:

> [!div class="nextstepaction"]
> [Creare e pubblicare un pacchetto usando l'interfaccia della riga di comando di DotNet](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla. Per informazioni su come seguire un'esercitazione su NuGet:

> [!div class="nextstepaction"]
> [Installare e usare un pacchetto con l'interfaccia della riga di comando di dotnet](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

Una libreria non deve essere distribuita come pacchetto. Può essere incluso in un'app console che lo usa. Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:

> [!div class="nextstepaction"]
> [Pubblicare un'applicazione console .NET Core con Visual Studio Code](publishing-with-visual-studio-code.md)
