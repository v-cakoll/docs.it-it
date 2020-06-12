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
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio-code"></a><span data-ttu-id="5d5ed-104">Esercitazione: testare una libreria di classi .NET Standard con .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5d5ed-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="5d5ed-105">Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d5ed-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5d5ed-106">Prerequisites</span></span>

- <span data-ttu-id="5d5ed-107">Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="5d5ed-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="5d5ed-108">Creare un progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="5d5ed-108">Create a unit test project</span></span>

<span data-ttu-id="5d5ed-109">Gli unit test forniscono test software automatici durante le fasi di sviluppo e pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="5d5ed-110">Il Framework di test usato in questa esercitazione è MSTest.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-110">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="5d5ed-111">[MSTest](https://github.com/Microsoft/testfx-docs) è uno dei tre Framework di test tra cui è possibile scegliere.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-111">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="5d5ed-112">Gli altri sono [xUnit](https://xunit.net/) e [NUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="5d5ed-112">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="5d5ed-113">Avviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="5d5ed-114">Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="5d5ed-114">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="5d5ed-115">Creare un progetto unit test denominato "StringLibraryTest".</span><span class="sxs-lookup"><span data-stu-id="5d5ed-115">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="5d5ed-116">Il modello di progetto crea un file UnitTest1.cs con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-116">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="5d5ed-117">Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-117">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="5d5ed-118">Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-118">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="5d5ed-119">Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="5d5ed-120">Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo da definire `TestMethod1` .</span><span class="sxs-lookup"><span data-stu-id="5d5ed-120">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="5d5ed-121">Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-121">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="5d5ed-122">Aggiungere il progetto di test alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-122">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="5d5ed-123">Aggiungere un riferimento al progetto</span><span class="sxs-lookup"><span data-stu-id="5d5ed-123">Add a project reference</span></span>

<span data-ttu-id="5d5ed-124">Per usare il progetto di test con la `StringLibrary` classe, aggiungere un riferimento al progetto nel progetto `StringLibraryTest` `StringLibrary` .</span><span class="sxs-lookup"><span data-stu-id="5d5ed-124">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="5d5ed-125">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-125">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="5d5ed-126">Aggiungere ed eseguire unit test metodi</span><span class="sxs-lookup"><span data-stu-id="5d5ed-126">Add and run unit test methods</span></span>

<span data-ttu-id="5d5ed-127">Quando Visual Studio esegue una unit test, viene eseguito ogni metodo contrassegnato con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo in una classe contrassegnata con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-127">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="5d5ed-128">Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-128">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="5d5ed-129">I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-129">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="5d5ed-130">Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-130">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="5d5ed-131">`Assert`Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-131">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="5d5ed-132">Metodi Assert</span><span class="sxs-lookup"><span data-stu-id="5d5ed-132">Assert methods</span></span>     | <span data-ttu-id="5d5ed-133">Funzione</span><span class="sxs-lookup"><span data-stu-id="5d5ed-133">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="5d5ed-134">Verifica che due oggetti o valori siano uguali.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-134">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="5d5ed-135">L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-135">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="5d5ed-136">Verifica che due variabili oggetto facciano riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-136">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="5d5ed-137">Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-137">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="5d5ed-138">Verifica che una condizione sia `false`.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-138">Verifies that a condition is `false`.</span></span> <span data-ttu-id="5d5ed-139">Il metodo ha esito negativo se la condizione è `true`.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-139">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="5d5ed-140">Verifica che un oggetto non sia `null` .</span><span class="sxs-lookup"><span data-stu-id="5d5ed-140">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="5d5ed-141">Il metodo ha esito negativo se l'oggetto è `null`.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-141">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="5d5ed-142">È anche possibile usare il <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodo in un metodo di test per indicare il tipo di eccezione che si prevede venga generata.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-142">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="5d5ed-143">Il test ha esito negativo se l'eccezione specificata non viene generata.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-143">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="5d5ed-144">Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-144">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="5d5ed-145">In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-145">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5d5ed-146">Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-146">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="5d5ed-147">In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-147">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="5d5ed-148">Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty) e un oggetto e una `null` stringa.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-148">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="5d5ed-149">Una stringa vuota non contiene caratteri e il cui valore <xref:System.String.Length> è 0.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-149">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="5d5ed-150">Una `null` stringa è una stringa che non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-150">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="5d5ed-151">È possibile chiamare `StartsWithUpper` direttamente come metodo statico e passare un singolo <xref:System.String> argomento.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-151">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="5d5ed-152">In alternativa, è possibile chiamare `StartsWithUpper` come metodo di estensione su una `string` variabile assegnata a `null` .</span><span class="sxs-lookup"><span data-stu-id="5d5ed-152">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="5d5ed-153">Verranno definiti tre metodi, ognuno dei quali chiama un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodo per ogni elemento in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-153">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="5d5ed-154">Si chiamerà un overload del metodo che consente di specificare un messaggio di errore da visualizzare in caso di errore del test.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-154">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="5d5ed-155">Il messaggio identifica la stringa che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-155">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="5d5ed-156">Per creare i metodi di test:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-156">To create the test methods:</span></span>

1. <span data-ttu-id="5d5ed-157">Aprire *StringLibraryTest/UnitTest1. cs* e sostituire tutto il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-157">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="5d5ed-158">Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-158">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="5d5ed-159">Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="5d5ed-159">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="5d5ed-160">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-160">Save your changes.</span></span>

1. <span data-ttu-id="5d5ed-161">Eseguire i test:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-161">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="5d5ed-162">L'output del terminale mostra che tutti i test sono stati superati.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-162">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="5d5ed-163">Gestione degli errori di test</span><span class="sxs-lookup"><span data-stu-id="5d5ed-163">Handle test failures</span></span>

<span data-ttu-id="5d5ed-164">Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-164">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="5d5ed-165">Si aggiunge quindi il codice all'app che rende il test riuscito.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-165">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="5d5ed-166">Per questa esercitazione è stato creato il test dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-166">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="5d5ed-167">Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-167">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="5d5ed-168">Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="5d5ed-168">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="5d5ed-169">Eseguire i test:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-169">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="5d5ed-170">L'output del terminale mostra che un test ha esito negativo e fornisce un messaggio di errore per il test non superato: "Assert. false non riuscito.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-170">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="5d5ed-171">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="5d5ed-171">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="5d5ed-172">A causa dell'errore, non sono state testate stringhe nella matrice dopo l'errore.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-172">Because of the failure, no strings in the array after "Error" were tested.</span></span>

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

1. <span data-ttu-id="5d5ed-173">Rimuovere la stringa "Error" aggiunta nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-173">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="5d5ed-174">Eseguire di nuovo il test e i test superati.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-174">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="5d5ed-175">Testare la versione di rilascio della libreria</span><span class="sxs-lookup"><span data-stu-id="5d5ed-175">Test the Release version of the library</span></span>

<span data-ttu-id="5d5ed-176">Ora che i test sono stati superati quando si esegue la build di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-176">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="5d5ed-177">Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-177">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="5d5ed-178">Eseguire i test con la configurazione della build di rilascio:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-178">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="5d5ed-179">I test avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-179">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5d5ed-180">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5d5ed-180">Additional resources</span></span>

* [<span data-ttu-id="5d5ed-181">Testing unità in .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="5d5ed-181">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="5d5ed-182">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5d5ed-182">Next steps</span></span>

<span data-ttu-id="5d5ed-183">In questa esercitazione è stata testata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-183">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="5d5ed-184">Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-184">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="5d5ed-185">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-185">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5d5ed-186">Creare e pubblicare un pacchetto usando l'interfaccia della riga di comando di DotNet</span><span class="sxs-lookup"><span data-stu-id="5d5ed-186">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="5d5ed-187">Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-187">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="5d5ed-188">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-188">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5d5ed-189">Installare e usare un pacchetto con l'interfaccia della riga di comando di dotnet</span><span class="sxs-lookup"><span data-stu-id="5d5ed-189">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="5d5ed-190">Una libreria non deve essere distribuita come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-190">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="5d5ed-191">Può essere incluso in un'app console che lo usa.</span><span class="sxs-lookup"><span data-stu-id="5d5ed-191">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="5d5ed-192">Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:</span><span class="sxs-lookup"><span data-stu-id="5d5ed-192">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5d5ed-193">Pubblicare un'applicazione console .NET Core con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5d5ed-193">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
