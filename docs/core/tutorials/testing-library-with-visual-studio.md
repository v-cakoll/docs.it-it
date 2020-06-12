---
title: Testare una libreria di classi di .NET Standard con .NET Core con Visual Studio
description: Creare un progetto unit test per una libreria di classi .NET Core. Verificare che una libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: f20b089fd22794d5aaeff34502e960fe41a565e1
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84700969"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio"></a><span data-ttu-id="92aa4-104">Esercitazione: testare una libreria di classi di .NET Standard con .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92aa4-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio</span></span>

<span data-ttu-id="92aa4-105">Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="92aa4-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92aa4-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="92aa4-106">Prerequisites</span></span>

- <span data-ttu-id="92aa4-107">Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="92aa4-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="92aa4-108">Creare un progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="92aa4-108">Create a unit test project</span></span>

<span data-ttu-id="92aa4-109">Gli unit test forniscono test software automatici durante le fasi di sviluppo e pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="92aa4-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="92aa4-110">[MSTest](https://github.com/Microsoft/testfx-docs) è uno dei tre Framework di test tra cui è possibile scegliere.</span><span class="sxs-lookup"><span data-stu-id="92aa4-110">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="92aa4-111">Gli altri sono [xUnit](https://xunit.net/) e [NUnit](https://nunit.org/).</span><span class="sxs-lookup"><span data-stu-id="92aa4-111">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="92aa4-112">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="92aa4-112">Start Visual Studio.</span></span>

1. <span data-ttu-id="92aa4-113">Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="92aa4-113">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="92aa4-114">Aggiungere un nuovo progetto unit test denominato "StringLibraryTest" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="92aa4-114">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="92aa4-115">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi**  >  **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-115">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="92aa4-116">Nella pagina **Aggiungi nuovo progetto** immettere **MSTest** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="92aa4-116">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="92aa4-117">Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.</span><span class="sxs-lookup"><span data-stu-id="92aa4-117">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="92aa4-118">Scegliere il modello **progetto di test MSTest (.NET Core)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-118">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="92aa4-119">Nella pagina **Configura nuovo progetto** immettere **StringLibraryTest** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="92aa4-119">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="92aa4-120">Scegli quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-120">Then choose **Create**.</span></span>

1. <span data-ttu-id="92aa4-121">Visual Studio crea il progetto e apre il file di classe nella finestra del codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="92aa4-121">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="92aa4-122">Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="92aa4-122">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports Microsoft.VisualStudio.TestTools.UnitTesting

   Namespace StringLibraryTest
       <TestClass>
       Public Class UnitTest1
           <TestMethod>
           Sub TestSub()

           End Sub
       End Class
   End Namespace
   ```

   <span data-ttu-id="92aa4-123">Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="92aa4-123">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="92aa4-124">Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.</span><span class="sxs-lookup"><span data-stu-id="92aa4-124">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="92aa4-125">Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="92aa4-125">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="92aa4-126">Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo per definire `TestMethod1` in C# o `TestSub` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="92aa4-126">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="92aa4-127">Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.</span><span class="sxs-lookup"><span data-stu-id="92aa4-127">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="92aa4-128">Aggiungere un riferimento al progetto</span><span class="sxs-lookup"><span data-stu-id="92aa4-128">Add a project reference</span></span>

<span data-ttu-id="92aa4-129">Affinché il progetto di test funzioni con la `StringLibrary` classe, aggiungere un riferimento al progetto nel progetto **StringLibraryTest** `StringLibrary` .</span><span class="sxs-lookup"><span data-stu-id="92aa4-129">For the test project to work with the `StringLibrary` class, add a reference in the **StringLibraryTest** project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="92aa4-130">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **dipendenze** del progetto **StringLibraryTest** e scegliere **Aggiungi riferimento al progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="92aa4-130">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="92aa4-131">Nella finestra di dialogo **Gestione riferimenti** espandere il nodo **progetti** , quindi selezionare la casella accanto a **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-131">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="92aa4-132">L'aggiunta di un riferimento all' `StringLibrary` assembly consente al compilatore di trovare i metodi **StringLibrary** durante la compilazione del progetto **StringLibraryTest** .</span><span class="sxs-lookup"><span data-stu-id="92aa4-132">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="92aa4-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-133">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="92aa4-134">Aggiungere ed eseguire unit test metodi</span><span class="sxs-lookup"><span data-stu-id="92aa4-134">Add and run unit test methods</span></span>

<span data-ttu-id="92aa4-135">Quando Visual Studio esegue una unit test, viene eseguito ogni metodo contrassegnato con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo in una classe contrassegnata con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="92aa4-135">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="92aa4-136">Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="92aa4-136">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="92aa4-137">I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="92aa4-137">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="92aa4-138">Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo.</span><span class="sxs-lookup"><span data-stu-id="92aa4-138">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="92aa4-139">`Assert`Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe:</span><span class="sxs-lookup"><span data-stu-id="92aa4-139">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="92aa4-140">Metodi Assert</span><span class="sxs-lookup"><span data-stu-id="92aa4-140">Assert methods</span></span>     | <span data-ttu-id="92aa4-141">Funzione</span><span class="sxs-lookup"><span data-stu-id="92aa4-141">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="92aa4-142">Verifica che due oggetti o valori siano uguali.</span><span class="sxs-lookup"><span data-stu-id="92aa4-142">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="92aa4-143">L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="92aa4-143">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="92aa4-144">Verifica che due variabili oggetto facciano riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="92aa4-144">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="92aa4-145">Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="92aa4-145">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="92aa4-146">Verifica che una condizione sia `false`.</span><span class="sxs-lookup"><span data-stu-id="92aa4-146">Verifies that a condition is `false`.</span></span> <span data-ttu-id="92aa4-147">Il metodo ha esito negativo se la condizione è `true`.</span><span class="sxs-lookup"><span data-stu-id="92aa4-147">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="92aa4-148">Verifica che un oggetto non sia `null` .</span><span class="sxs-lookup"><span data-stu-id="92aa4-148">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="92aa4-149">Il metodo ha esito negativo se l'oggetto è `null`.</span><span class="sxs-lookup"><span data-stu-id="92aa4-149">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="92aa4-150">È anche possibile usare il <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodo in un metodo di test per indicare il tipo di eccezione che si prevede venga generata.</span><span class="sxs-lookup"><span data-stu-id="92aa4-150">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="92aa4-151">Il test ha esito negativo se l'eccezione specificata non viene generata.</span><span class="sxs-lookup"><span data-stu-id="92aa4-151">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="92aa4-152">Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="92aa4-152">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="92aa4-153">In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="92aa4-153">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="92aa4-154">Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="92aa4-154">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="92aa4-155">In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="92aa4-155">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="92aa4-156">Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty), una stringa valida senza caratteri e il cui valore <xref:System.String.Length> è 0 e una `null` stringa che non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="92aa4-156">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="92aa4-157">È possibile chiamare `StartsWithUpper` direttamente come metodo statico e passare un singolo <xref:System.String> argomento.</span><span class="sxs-lookup"><span data-stu-id="92aa4-157">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="92aa4-158">In alternativa, è possibile chiamare `StartsWithUpper` come metodo di estensione su una `string` variabile assegnata a `null` .</span><span class="sxs-lookup"><span data-stu-id="92aa4-158">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="92aa4-159">Verranno definiti tre metodi, ognuno dei quali chiama un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodo per ogni elemento in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="92aa4-159">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="92aa4-160">Si chiamerà un overload del metodo che consente di specificare un messaggio di errore da visualizzare in caso di errore del test.</span><span class="sxs-lookup"><span data-stu-id="92aa4-160">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="92aa4-161">Il messaggio identifica la stringa che ha causato l'errore.</span><span class="sxs-lookup"><span data-stu-id="92aa4-161">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="92aa4-162">Per creare i metodi di test:</span><span class="sxs-lookup"><span data-stu-id="92aa4-162">To create the test methods:</span></span>

1. <span data-ttu-id="92aa4-163">Nella finestra del codice *UnitTest1.cs* o *UnitTest1. vb* sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="92aa4-163">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="92aa4-164">Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico.</span><span class="sxs-lookup"><span data-stu-id="92aa4-164">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="92aa4-165">Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="92aa4-165">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="92aa4-166">Nella barra dei menu selezionare **file**  >  **Salva UnitTest1.cs come** o **file**  >  **Salva UnitTest1. vb con nome**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-166">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="92aa4-167">Nella finestra di dialogo **Salva file con nome** selezionare la freccia accanto al pulsante **Salva** e selezionare **Salva con codifica**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-167">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92aa4-168">![Finestra di dialogo Salva file con nome di Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="92aa4-168">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="92aa4-169">Nella finestra di dialogo **Conferma Salva con nome** selezionare il pulsante **Sì** per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="92aa4-169">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="92aa4-170">Nella finestra di dialogo **Opzioni di salvataggio avanzate** selezionare **Unicode (UTF-8 con firma digitale) - Tabella codici 65001** dall'elenco a discesa **Codifica** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-170">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92aa4-171">![Finestra di dialogo di Visual Studio Opzioni di salvataggio avanzate](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="92aa4-171">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="92aa4-172">Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII.</span><span class="sxs-lookup"><span data-stu-id="92aa4-172">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="92aa4-173">In tal caso, il runtime non decodifica accuratamente i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.</span><span class="sxs-lookup"><span data-stu-id="92aa4-173">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="92aa4-174">Sulla barra dei menu selezionare **test**  >  **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-174">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="92aa4-175">Se la finestra **Esplora test** non viene aperta, aprirla **scegliendo**  >  **Esplora test**test.</span><span class="sxs-lookup"><span data-stu-id="92aa4-175">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="92aa4-176">I tre test sono elencati nella sezione **Test superati** e nella sezione **Riepilogo** è riportato il risultato dell'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="92aa4-176">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92aa4-177">![Finestra di Esplora test con i test riusciti](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="92aa4-177">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="92aa4-178">Gestione degli errori di test</span><span class="sxs-lookup"><span data-stu-id="92aa4-178">Handle test failures</span></span>

<span data-ttu-id="92aa4-179">Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="92aa4-179">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="92aa4-180">Si aggiunge quindi il codice all'app che rende il test riuscito.</span><span class="sxs-lookup"><span data-stu-id="92aa4-180">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="92aa4-181">Per questa esercitazione è stato creato il test dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="92aa4-181">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="92aa4-182">Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.</span><span class="sxs-lookup"><span data-stu-id="92aa4-182">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="92aa4-183">Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="92aa4-183">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="92aa4-184">Non è necessario salvare il file perché Visual Studio salva i file aperti automaticamente quando viene creata una soluzione per eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="92aa4-184">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="92aa4-185">Eseguire il test selezionando **test**  >  **Esegui tutti i test** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="92aa4-185">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="92aa4-186">La finestra **Esplora test** indica che due test hanno avuto esito positivo e uno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="92aa4-186">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92aa4-187">![Finestra di Esplora test con i test non riusciti](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="92aa4-187">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="92aa4-188">Selezionare il test non superato `TestDoesNotStartWith` .</span><span class="sxs-lookup"><span data-stu-id="92aa4-188">Select the failed test, `TestDoesNotStartWith`.</span></span>

   <span data-ttu-id="92aa4-189">Nella finestra **Esplora test** viene visualizzato il messaggio generato dal metodo Assert: "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="92aa4-189">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="92aa4-190">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="92aa4-190">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="92aa4-191">A causa dell'errore, non sono state testate stringhe nella matrice dopo l'errore.</span><span class="sxs-lookup"><span data-stu-id="92aa4-191">Because of the failure, no strings in the array after "Error" were tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92aa4-192">![Finestra Esplora test che mostra l'errore di asserzione false](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="92aa4-192">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="92aa4-193">Rimuovere la stringa "Error" aggiunta nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="92aa4-193">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="92aa4-194">Eseguire di nuovo il test e i test superati.</span><span class="sxs-lookup"><span data-stu-id="92aa4-194">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="92aa4-195">Testare la versione di rilascio della libreria</span><span class="sxs-lookup"><span data-stu-id="92aa4-195">Test the Release version of the library</span></span>

<span data-ttu-id="92aa4-196">Ora che i test sono stati superati quando si esegue la build di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria.</span><span class="sxs-lookup"><span data-stu-id="92aa4-196">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="92aa4-197">Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.</span><span class="sxs-lookup"><span data-stu-id="92aa4-197">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="92aa4-198">Per testare la versione di rilascio, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="92aa4-198">To test the Release build:</span></span>

1. <span data-ttu-id="92aa4-199">Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-199">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92aa4-200">![Barra degli strumenti di Visual Studio con la configurazione di rilascio evidenziata](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="92aa4-200">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="92aa4-201">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **StringLibrary** e selezionare **Compila** dal menu di scelta rapida per ricompilare la libreria.</span><span class="sxs-lookup"><span data-stu-id="92aa4-201">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92aa4-202">![Menu di scelta rapida StringLibrary con il comando di compilazione](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="92aa4-202">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="92aa4-203">Eseguire gli unit test scegliendo **test Esegui**  >  **tutti i test** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="92aa4-203">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="92aa4-204">I test avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="92aa4-204">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92aa4-205">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="92aa4-205">Additional resources</span></span>

* [<span data-ttu-id="92aa4-206">Nozioni fondamentali sugli unit test di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92aa4-206">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
* [<span data-ttu-id="92aa4-207">Testing unità in .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="92aa4-207">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="92aa4-208">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="92aa4-208">Next steps</span></span>

<span data-ttu-id="92aa4-209">In questa esercitazione è stata testata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="92aa4-209">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="92aa4-210">Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="92aa4-210">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="92aa4-211">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="92aa4-211">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92aa4-212">Creare e pubblicare un pacchetto NuGet con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92aa4-212">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="92aa4-213">Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla.</span><span class="sxs-lookup"><span data-stu-id="92aa4-213">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="92aa4-214">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="92aa4-214">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92aa4-215">Installare e usare un pacchetto in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92aa4-215">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="92aa4-216">Una libreria non deve essere distribuita come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="92aa4-216">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="92aa4-217">Può essere incluso in un'app console che lo usa.</span><span class="sxs-lookup"><span data-stu-id="92aa4-217">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="92aa4-218">Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:</span><span class="sxs-lookup"><span data-stu-id="92aa4-218">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92aa4-219">Pubblicare un'applicazione console .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92aa4-219">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
