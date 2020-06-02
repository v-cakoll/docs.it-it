---
title: Testare una libreria di classi .NET Standard con .NET Core in Visual Studio Code
description: Creare un progetto unit test per una libreria di classi .NET Core. Verificare che una libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 05/29/2020
ms.openlocfilehash: be227453bd441028cc6ce348c00fad944140238f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292189"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio-code"></a><span data-ttu-id="8cf14-104">Esercitazione: testare una libreria di .NET Standard con .NET Core in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8cf14-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>

<span data-ttu-id="8cf14-105">Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="8cf14-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cf14-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8cf14-106">Prerequisites</span></span>

- <span data-ttu-id="8cf14-107">Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio Code](library-with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="8cf14-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="8cf14-108">Creare un progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="8cf14-108">Create a unit test project</span></span>

1. <span data-ttu-id="8cf14-109">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8cf14-109">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="8cf14-110">Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8cf14-110">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="8cf14-111">Creare un progetto unit test denominato "StringLibraryTest".</span><span class="sxs-lookup"><span data-stu-id="8cf14-111">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="8cf14-112">Il modello di progetto crea un file UnitTest1.cs con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8cf14-112">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="8cf14-113">Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cf14-113">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="8cf14-114">Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.</span><span class="sxs-lookup"><span data-stu-id="8cf14-114">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="8cf14-115">Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="8cf14-115">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="8cf14-116">Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo da definire `TestMethod1` .</span><span class="sxs-lookup"><span data-stu-id="8cf14-116">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="8cf14-117">Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.</span><span class="sxs-lookup"><span data-stu-id="8cf14-117">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8cf14-118">MSTest è uno dei tre Framework di test tra cui è possibile scegliere.</span><span class="sxs-lookup"><span data-stu-id="8cf14-118">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="8cf14-119">Gli altri sono xUnit e nUnit.</span><span class="sxs-lookup"><span data-stu-id="8cf14-119">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="8cf14-120">Aggiungere il progetto di test alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="8cf14-120">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

1. <span data-ttu-id="8cf14-121">Creare un riferimento al progetto di libreria di classi eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8cf14-121">Create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="8cf14-122">Aggiungere ed eseguire unit test metodi</span><span class="sxs-lookup"><span data-stu-id="8cf14-122">Add and run unit test methods</span></span>

<span data-ttu-id="8cf14-123">Quando Visual Studio esegue una unit test, viene eseguito ogni metodo contrassegnato con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo in una classe contrassegnata con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="8cf14-123">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="8cf14-124">Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8cf14-124">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="8cf14-125">I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="8cf14-125">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="8cf14-126">Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo.</span><span class="sxs-lookup"><span data-stu-id="8cf14-126">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="8cf14-127">`Assert`Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe:</span><span class="sxs-lookup"><span data-stu-id="8cf14-127">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="8cf14-128">Metodi Assert</span><span class="sxs-lookup"><span data-stu-id="8cf14-128">Assert methods</span></span>     | <span data-ttu-id="8cf14-129">Funzione</span><span class="sxs-lookup"><span data-stu-id="8cf14-129">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="8cf14-130">Verifica che due oggetti o valori siano uguali.</span><span class="sxs-lookup"><span data-stu-id="8cf14-130">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="8cf14-131">L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="8cf14-131">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="8cf14-132">Verifica che due variabili oggetto facciano riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="8cf14-132">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="8cf14-133">Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="8cf14-133">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="8cf14-134">Verifica che una condizione sia `false`.</span><span class="sxs-lookup"><span data-stu-id="8cf14-134">Verifies that a condition is `false`.</span></span> <span data-ttu-id="8cf14-135">Il metodo ha esito negativo se la condizione è `true`.</span><span class="sxs-lookup"><span data-stu-id="8cf14-135">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="8cf14-136">Verifica che un oggetto non sia `null` .</span><span class="sxs-lookup"><span data-stu-id="8cf14-136">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="8cf14-137">Il metodo ha esito negativo se l'oggetto è `null`.</span><span class="sxs-lookup"><span data-stu-id="8cf14-137">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="8cf14-138">È anche possibile usare il <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodo in un metodo di test per indicare il tipo di eccezione che si prevede venga generata.</span><span class="sxs-lookup"><span data-stu-id="8cf14-138">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="8cf14-139">Il test ha esito negativo se l'eccezione specificata non viene generata.</span><span class="sxs-lookup"><span data-stu-id="8cf14-139">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="8cf14-140">Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="8cf14-140">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="8cf14-141">In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8cf14-141">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="8cf14-142">Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="8cf14-142">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="8cf14-143">In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8cf14-143">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8cf14-144">Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty) e un oggetto e una `null` stringa.</span><span class="sxs-lookup"><span data-stu-id="8cf14-144">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="8cf14-145">Una stringa vuota non contiene caratteri e il cui valore <xref:System.String.Length> è 0.</span><span class="sxs-lookup"><span data-stu-id="8cf14-145">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="8cf14-146">Una `null` stringa è una stringa che non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="8cf14-146">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="8cf14-147">È possibile chiamare `StartsWithUpper` direttamente come metodo statico e passare un singolo <xref:System.String> argomento.</span><span class="sxs-lookup"><span data-stu-id="8cf14-147">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="8cf14-148">In alternativa, è possibile chiamare `StartsWithUpper` come metodo di estensione su una `string` variabile assegnata a `null` .</span><span class="sxs-lookup"><span data-stu-id="8cf14-148">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="8cf14-149">Verranno definiti tre metodi, ognuno dei quali chiama <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> ripetutamente un metodo per ogni elemento in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="8cf14-149">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="8cf14-150">Poiché il metodo di test ha esito negativo non appena viene trovato il primo errore, verrà chiamato un overload del metodo che consente di passare una stringa che indica il valore stringa usato nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="8cf14-150">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="8cf14-151">Per creare i metodi di test:</span><span class="sxs-lookup"><span data-stu-id="8cf14-151">To create the test methods:</span></span>

1. <span data-ttu-id="8cf14-152">Aprire *StringLibraryTest/UnitTest1. cs* e sostituire tutto il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8cf14-152">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="8cf14-153">Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico.</span><span class="sxs-lookup"><span data-stu-id="8cf14-153">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="8cf14-154">Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="8cf14-154">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="8cf14-155">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8cf14-155">Save your changes.</span></span>

1. <span data-ttu-id="8cf14-156">Eseguire i test:</span><span class="sxs-lookup"><span data-stu-id="8cf14-156">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="8cf14-157">L'output del terminale mostra che tutti i test sono stati superati.</span><span class="sxs-lookup"><span data-stu-id="8cf14-157">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="8cf14-158">Gestione degli errori di test</span><span class="sxs-lookup"><span data-stu-id="8cf14-158">Handle test failures</span></span>

<span data-ttu-id="8cf14-159">Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="8cf14-159">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="8cf14-160">Si aggiunge quindi il codice all'app che rende il test riuscito.</span><span class="sxs-lookup"><span data-stu-id="8cf14-160">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="8cf14-161">In questo caso, il test è stato creato dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="8cf14-161">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="8cf14-162">Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.</span><span class="sxs-lookup"><span data-stu-id="8cf14-162">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="8cf14-163">Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="8cf14-163">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="8cf14-164">Eseguire i test:</span><span class="sxs-lookup"><span data-stu-id="8cf14-164">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="8cf14-165">L'output del terminale mostra che un test ha esito negativo e fornisce un messaggio di errore per il test non superato.</span><span class="sxs-lookup"><span data-stu-id="8cf14-165">The terminal output shows that one test fails, and it provides an error message for the failed test.</span></span>

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

1. <span data-ttu-id="8cf14-166">Annullare la modifica apportata nel passaggio 1 e rimuovere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="8cf14-166">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="8cf14-167">Eseguire di nuovo il test e i test superati.</span><span class="sxs-lookup"><span data-stu-id="8cf14-167">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="8cf14-168">Testare la versione di rilascio della libreria</span><span class="sxs-lookup"><span data-stu-id="8cf14-168">Test the Release version of the library</span></span>

<span data-ttu-id="8cf14-169">Ora che i test sono stati superati quando si esegue la versione di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria.</span><span class="sxs-lookup"><span data-stu-id="8cf14-169">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="8cf14-170">Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.</span><span class="sxs-lookup"><span data-stu-id="8cf14-170">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="8cf14-171">Eseguire i test con la configurazione della build di rilascio:</span><span class="sxs-lookup"><span data-stu-id="8cf14-171">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="8cf14-172">I test avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8cf14-172">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8cf14-173">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8cf14-173">Additional resources</span></span>

- [<span data-ttu-id="8cf14-174">Testing unità in .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="8cf14-174">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="8cf14-175">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8cf14-175">Next steps</span></span>

<span data-ttu-id="8cf14-176">In questa esercitazione è stata testata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="8cf14-176">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="8cf14-177">Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8cf14-177">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="8cf14-178">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="8cf14-178">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8cf14-179">Creare e pubblicare un pacchetto usando l'interfaccia della riga di comando di DotNet</span><span class="sxs-lookup"><span data-stu-id="8cf14-179">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="8cf14-180">Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla.</span><span class="sxs-lookup"><span data-stu-id="8cf14-180">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="8cf14-181">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="8cf14-181">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8cf14-182">Installare e usare un pacchetto con l'interfaccia della riga di comando di dotnet</span><span class="sxs-lookup"><span data-stu-id="8cf14-182">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="8cf14-183">Una libreria non deve essere distribuita come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8cf14-183">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="8cf14-184">Può essere incluso in un'app console che lo usa.</span><span class="sxs-lookup"><span data-stu-id="8cf14-184">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="8cf14-185">Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:</span><span class="sxs-lookup"><span data-stu-id="8cf14-185">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8cf14-186">Pubblicare un'applicazione console .NET Core con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8cf14-186">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
