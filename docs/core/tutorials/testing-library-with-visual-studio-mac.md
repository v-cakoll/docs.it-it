---
title: Testare una libreria di classi .NET Standard con .NET Core usando Visual Studio per Mac
description: Creare un progetto unit test per una libreria di classi .NET Core. Verificare che una libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 06/08/2020
ms.openlocfilehash: a183049623df44cbb8c4abd47ce6e78d91adae12
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713609"
---
# <a name="test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="f86fc-104">Testare una libreria di classi di .NET Standard con .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f86fc-104">Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="f86fc-105">Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="f86fc-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f86fc-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f86fc-106">Prerequisites</span></span>

- <span data-ttu-id="f86fc-107">Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio per Mac](library-with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="f86fc-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="f86fc-108">Creare un progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="f86fc-108">Create a unit test project</span></span>

<span data-ttu-id="f86fc-109">Gli unit test forniscono test software automatici durante le fasi di sviluppo e pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f86fc-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="f86fc-110">[MSTest](https://github.com/Microsoft/testfx-docs) è uno dei tre Framework di test tra cui è possibile scegliere.</span><span class="sxs-lookup"><span data-stu-id="f86fc-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="f86fc-111">Gli altri sono [xUnit](https://xunit.net/) e [NUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="f86fc-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="f86fc-112">Avviare Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="f86fc-112">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="f86fc-113">Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET Standard in Visual Studio per Mac](library-with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="f86fc-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio for Mac](library-with-visual-studio-mac.md).</span></span>

1. <span data-ttu-id="f86fc-114">Nel riquadro della **soluzione** , fare clic con il <kbd>pulsante destro del</kbd>mouse sulla `ClassLibraryProjects` soluzione e scegliere **Aggiungi**  >  **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-114">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="f86fc-115">Nella finestra di dialogo **nuovo progetto** selezionare **test** dal nodo **console e Web** .</span><span class="sxs-lookup"><span data-stu-id="f86fc-115">In the **New Project** dialog, select **Tests** from the **Web and Console** node.</span></span> <span data-ttu-id="f86fc-116">Selezionare il **progetto MSTest** seguito da **Next**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-116">Select the **MSTest Project** followed by **Next**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-project.png" alt-text="Finestra di dialogo nuovo progetto di Visual Studio Mac Creazione progetto di test":::

1. <span data-ttu-id="f86fc-118">Selezionare **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-118">Select **.NET Core 3.1**.</span></span> <span data-ttu-id="f86fc-119">Assegnare al nuovo progetto il nome "StringLibraryTest" e selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-119">Name the new project "StringLibraryTest" and select **Create**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-new-project-name.png" alt-text="Finestra di dialogo Nuovo progetto di Visual Studio per Mac in cui si specifica il nome del progetto":::

   <span data-ttu-id="f86fc-121">Visual Studio crea un file di classe con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f86fc-121">Visual Studio creates a class file with the following code:</span></span>

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

   <span data-ttu-id="f86fc-122">Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f86fc-122">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="f86fc-123">Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.</span><span class="sxs-lookup"><span data-stu-id="f86fc-123">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="f86fc-124">Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="f86fc-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="f86fc-125">Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo a `TestMethod1` .</span><span class="sxs-lookup"><span data-stu-id="f86fc-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to `TestMethod1`.</span></span>

   <span data-ttu-id="f86fc-126">Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.</span><span class="sxs-lookup"><span data-stu-id="f86fc-126">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="f86fc-127">Aggiungere un riferimento al progetto</span><span class="sxs-lookup"><span data-stu-id="f86fc-127">Add a project reference</span></span>

<span data-ttu-id="f86fc-128">Per usare il progetto di test con la `StringLibrary` classe, aggiungere un riferimento al `StringLibrary` progetto.</span><span class="sxs-lookup"><span data-stu-id="f86fc-128">For the test project to work with the `StringLibrary` class, add a reference to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="f86fc-129">Nel riquadro della **soluzione** , <kbd>fare</kbd>clic su **dipendenze** sotto **StringLibraryTest**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-129">In the **Solution** pad, <kbd>ctrl</kbd>-click **Dependencies** under **StringLibraryTest**.</span></span> <span data-ttu-id="f86fc-130">Scegliere **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f86fc-130">Select **Add Reference** from the context menu.</span></span>

1. <span data-ttu-id="f86fc-131">Nella finestra di dialogo **riferimenti** selezionare il progetto **StringLibrary** .</span><span class="sxs-lookup"><span data-stu-id="f86fc-131">In the **References** dialog, select the **StringLibrary** project.</span></span> <span data-ttu-id="f86fc-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-132">Select **OK**.</span></span>

      :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-edit-references.png" alt-text="Finestra di dialogo Modifica riferimenti di Visual Studio per Mac":::

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="f86fc-134">Aggiungere ed eseguire unit test metodi</span><span class="sxs-lookup"><span data-stu-id="f86fc-134">Add and run unit test methods</span></span>

<span data-ttu-id="f86fc-135">Quando Visual Studio esegue una unit test, viene eseguito ogni metodo contrassegnato con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo in una classe contrassegnata con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="f86fc-136">Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="f86fc-137">I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="f86fc-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="f86fc-138">Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="f86fc-139">`Assert`Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe:</span><span class="sxs-lookup"><span data-stu-id="f86fc-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="f86fc-140">Metodi Assert</span><span class="sxs-lookup"><span data-stu-id="f86fc-140">Assert methods</span></span>     | <span data-ttu-id="f86fc-141">Funzione</span><span class="sxs-lookup"><span data-stu-id="f86fc-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="f86fc-142">Verifica che due oggetti o valori siano uguali.</span><span class="sxs-lookup"><span data-stu-id="f86fc-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="f86fc-143">L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="f86fc-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="f86fc-144">Verifica che due variabili oggetto facciano riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="f86fc-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="f86fc-145">Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="f86fc-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="f86fc-146">Verifica che una condizione sia `false`.</span><span class="sxs-lookup"><span data-stu-id="f86fc-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="f86fc-147">Il metodo ha esito negativo se la condizione è `true`.</span><span class="sxs-lookup"><span data-stu-id="f86fc-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="f86fc-148">Verifica che un oggetto non sia `null` .</span><span class="sxs-lookup"><span data-stu-id="f86fc-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="f86fc-149">Il metodo ha esito negativo se l'oggetto è `null`.</span><span class="sxs-lookup"><span data-stu-id="f86fc-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="f86fc-150">È anche possibile usare il <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodo in un metodo di test per indicare il tipo di eccezione che si prevede venga generata.</span><span class="sxs-lookup"><span data-stu-id="f86fc-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="f86fc-151">Il test ha esito negativo se l'eccezione specificata non viene generata.</span><span class="sxs-lookup"><span data-stu-id="f86fc-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="f86fc-152">Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="f86fc-153">In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f86fc-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f86fc-154">Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="f86fc-155">In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f86fc-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f86fc-156">Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty), una stringa valida senza caratteri e il cui valore <xref:System.String.Length> è 0 e una `null` stringa che non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="f86fc-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="f86fc-157">È possibile chiamare `StartsWithUpper` direttamente come metodo statico e passare un singolo <xref:System.String> argomento.</span><span class="sxs-lookup"><span data-stu-id="f86fc-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="f86fc-158">In alternativa, è possibile chiamare `StartsWithUpper` come metodo di estensione su una `string` variabile assegnata a `null` .</span><span class="sxs-lookup"><span data-stu-id="f86fc-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="f86fc-159">Verranno definiti tre metodi, ognuno dei quali chiama un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodo per ogni elemento in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="f86fc-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="f86fc-160">Si chiamerà un overload del metodo che consente di specificare un messaggio di errore da visualizzare in caso di errore del test.</span><span class="sxs-lookup"><span data-stu-id="f86fc-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="f86fc-161">Il messaggio identifica la stringa che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="f86fc-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="f86fc-162">Per creare i metodi di test:</span><span class="sxs-lookup"><span data-stu-id="f86fc-162">To create the test methods:</span></span>

1. <span data-ttu-id="f86fc-163">Aprire il file *UnitTest1.cs* e sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f86fc-163">Open the *UnitTest1.cs* file and replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="f86fc-164">Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico.</span><span class="sxs-lookup"><span data-stu-id="f86fc-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="f86fc-165">Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="f86fc-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="f86fc-166">Nella barra dei menu selezionare **file**  >  **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-166">On the menu bar, select **File** > **Save As**.</span></span> <span data-ttu-id="f86fc-167">Nella finestra di dialogo verificare che **Encoding** sia impostato su **Unicode (UTF-8)**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-167">In the dialog, make sure that **Encoding** is set to **Unicode (UTF-8)**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/save-file-as-dialog.png" alt-text="Finestra di dialogo Salva file con nome di Visual Studio":::

1. <span data-ttu-id="f86fc-169">Quando viene chiesto se si desidera sostituire il file esistente, selezionare **Sostituisci**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-169">When you're asked if you want to replace the existing file, select **Replace**.</span></span>

   <span data-ttu-id="f86fc-170">Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII.</span><span class="sxs-lookup"><span data-stu-id="f86fc-170">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="f86fc-171">In tal caso, il runtime non decodifica accuratamente i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.</span><span class="sxs-lookup"><span data-stu-id="f86fc-171">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="f86fc-172">Aprire il pannello **Unit test** sul lato destro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-172">Open the **Unit Tests** panel on the right side of the screen.</span></span> <span data-ttu-id="f86fc-173">Selezionare **Visualizza**  >  **test** dal menu.</span><span class="sxs-lookup"><span data-stu-id="f86fc-173">Select **View** > **Tests** from the menu.</span></span>

1. <span data-ttu-id="f86fc-174">Fare clic sull'icona **Ancora** per mantenere aperto il pannello.</span><span class="sxs-lookup"><span data-stu-id="f86fc-174">Click the **Dock** icon to keep the panel open.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-dock-icon.png" alt-text="Icona di ancoraggio del pannello degli unit test di Visual Studio per Mac":::

1. <span data-ttu-id="f86fc-176">Fare clic sul pulsante **Esegui tutto**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-176">Click the **Run All** button.</span></span>

   <span data-ttu-id="f86fc-177">Tutti i test hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-177">All tests pass.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-pass.png" alt-text="Visual Studio per Mac sessioni di test previste":::

## <a name="handle-test-failures"></a><span data-ttu-id="f86fc-179">Gestione degli errori di test</span><span class="sxs-lookup"><span data-stu-id="f86fc-179">Handle test failures</span></span>

<span data-ttu-id="f86fc-180">Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="f86fc-180">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="f86fc-181">Si aggiunge quindi il codice all'app che rende il test riuscito.</span><span class="sxs-lookup"><span data-stu-id="f86fc-181">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="f86fc-182">Per questa esercitazione è stato creato il test dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="f86fc-182">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="f86fc-183">Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.</span><span class="sxs-lookup"><span data-stu-id="f86fc-183">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="f86fc-184">Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="f86fc-184">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="f86fc-185">Non è necessario salvare il file perché Visual Studio salva i file aperti automaticamente quando viene creata una soluzione per eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="f86fc-185">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="f86fc-186">Eseguire di nuovo i test.</span><span class="sxs-lookup"><span data-stu-id="f86fc-186">Run the tests again.</span></span>

   <span data-ttu-id="f86fc-187">Questa volta, la finestra **Esplora test** indica che due test hanno avuto esito positivo e uno non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="f86fc-187">This time, the **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/failed-test-window.png" alt-text="Finestra di Esplora test con i test non riusciti":::

1. <span data-ttu-id="f86fc-189"><kbd>premere CTRL</kbd>e fare clic sul test non superato, `TestDoesNotStartWithUpper` quindi selezionare **Mostra riquadro risultati** nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f86fc-189"><kbd>ctrl</kbd>-click the failed test, `TestDoesNotStartWithUpper`, and select **Show Results Pad** from the context menu.</span></span>

   <span data-ttu-id="f86fc-190">Nel riquadro **dei risultati** viene visualizzato il messaggio prodotto dall'asserzione: "Assert. false non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="f86fc-190">The **Results** pad displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="f86fc-191">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="f86fc-191">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="f86fc-192">A causa dell'errore, non sono state testate stringhe nella matrice dopo l'errore.</span><span class="sxs-lookup"><span data-stu-id="f86fc-192">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-mac-unit-test-failure.png" alt-text="Finestra Esplora test che mostra l'errore di asserzione false":::

1. <span data-ttu-id="f86fc-194">Rimuovere la stringa "Error" aggiunta nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="f86fc-194">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="f86fc-195">Eseguire di nuovo il test e i test superati.</span><span class="sxs-lookup"><span data-stu-id="f86fc-195">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="f86fc-196">Testare la versione di rilascio della libreria</span><span class="sxs-lookup"><span data-stu-id="f86fc-196">Test the Release version of the library</span></span>

<span data-ttu-id="f86fc-197">Ora che i test sono stati superati quando si esegue la build di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria.</span><span class="sxs-lookup"><span data-stu-id="f86fc-197">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="f86fc-198">Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.</span><span class="sxs-lookup"><span data-stu-id="f86fc-198">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="f86fc-199">Per testare la versione di rilascio, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="f86fc-199">To test the Release build:</span></span>

1. <span data-ttu-id="f86fc-200">Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="f86fc-200">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra degli strumenti di Visual Studio con la configurazione di rilascio evidenziata":::

1. <span data-ttu-id="f86fc-202">Nel riquadro della **soluzione** , fare clic con il <kbd>pulsante destro del</kbd>mouse sul progetto **StringLibrary** e scegliere **Compila** dal menu di scelta rapida per ricompilare la libreria.</span><span class="sxs-lookup"><span data-stu-id="f86fc-202">In the **Solution** pad, <kbd>ctrl</kbd>-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   :::image type="content" source="media/testing-library-with-visual-studio-mac/build-library-context-menu.png" alt-text="Menu di scelta rapida StringLibrary con il comando di compilazione":::

1. <span data-ttu-id="f86fc-204">Eseguire di nuovo gli unit test.</span><span class="sxs-lookup"><span data-stu-id="f86fc-204">Run the unit tests again.</span></span>

   <span data-ttu-id="f86fc-205">I test avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f86fc-205">The tests pass.</span></span>

## <a name="debug-tests"></a><span data-ttu-id="f86fc-206">Esecuzione del debug dei test</span><span class="sxs-lookup"><span data-stu-id="f86fc-206">Debug tests</span></span>

<span data-ttu-id="f86fc-207">È possibile usare lo stesso processo illustrato in [esercitazione: eseguire il debug di un'applicazione console .NET Core usando Visual Studio per Mac](debugging-with-visual-studio-mac.md) per eseguire il debug del codice usando il progetto unit test.</span><span class="sxs-lookup"><span data-stu-id="f86fc-207">You can use the same process shown in [Tutorial: Debug a .NET Core console application using Visual Studio for Mac](debugging-with-visual-studio-mac.md) to debug code using your unit test project.</span></span> <span data-ttu-id="f86fc-208">Anziché avviare il progetto di app ShowCase, fare clic con il <kbd>pulsante destro del</kbd>mouse sul progetto **StringLibraryTests** e scegliere **Avvia progetto di debug** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f86fc-208">Instead of starting the ShowCase app project, <kbd>ctrl</kbd>-click the **StringLibraryTests** project, and select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="f86fc-209">Visual Studio avvia il progetto di test con il debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="f86fc-209">Visual Studio starts the test project with the debugger attached.</span></span> <span data-ttu-id="f86fc-210">L'esecuzione si arresterà in corrispondenza di qualsiasi punto di interruzione aggiunto al progetto di test o al codice della libreria sottostante.</span><span class="sxs-lookup"><span data-stu-id="f86fc-210">Execution will stop at any breakpoint you've added to the test project or the underlying library code.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f86fc-211">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f86fc-211">Additional resources</span></span>

* [<span data-ttu-id="f86fc-212">Testing unità in .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="f86fc-212">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="f86fc-213">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f86fc-213">Next steps</span></span>

<span data-ttu-id="f86fc-214">In questa esercitazione è stata testata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="f86fc-214">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="f86fc-215">Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f86fc-215">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="f86fc-216">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="f86fc-216">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f86fc-217">Creare e pubblicare un pacchetto (interfaccia della riga di comando dotnet)</span><span class="sxs-lookup"><span data-stu-id="f86fc-217">Create and publish a package (dotnet CLI)</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="f86fc-218">Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla.</span><span class="sxs-lookup"><span data-stu-id="f86fc-218">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="f86fc-219">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="f86fc-219">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f86fc-220">Installare e usare un pacchetto in Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="f86fc-220">Install and use a package in Visual Studio for Mac</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

<span data-ttu-id="f86fc-221">Una libreria non deve essere distribuita come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f86fc-221">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="f86fc-222">Può essere incluso in un'app console che lo usa.</span><span class="sxs-lookup"><span data-stu-id="f86fc-222">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="f86fc-223">Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:</span><span class="sxs-lookup"><span data-stu-id="f86fc-223">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f86fc-224">Pubblicare un'applicazione console .NET Core con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="f86fc-224">Publish a .NET Core console application with Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
