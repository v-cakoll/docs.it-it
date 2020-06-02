---
title: Testare una libreria di classi .NET Standard con .NET Core in Visual Studio
description: Creare un progetto di unit test per la libreria di classi .NET Core. Verificare che la libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 48ada77b8422030fd93aa29df1df50a3ae5104fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283507"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="637b4-104">Esercitazione: testare una libreria di .NET Standard con .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="637b4-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="637b4-105">Questa esercitazione illustra come automatizzare gli unit test aggiungendo un progetto di test a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="637b4-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="637b4-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="637b4-106">Prerequisites</span></span>

- <span data-ttu-id="637b4-107">Questa esercitazione funziona con la soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="637b4-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="637b4-108">Creare un progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="637b4-108">Create a unit test project</span></span>

1. <span data-ttu-id="637b4-109">Aprire la `ClassLibraryProjects` soluzione creata in [creare una libreria di .NET standard in Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="637b4-109">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="637b4-110">Aggiungere un nuovo progetto unit test denominato "StringLibraryTest" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="637b4-110">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="637b4-111">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi**  >  **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="637b4-111">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="637b4-112">Nella pagina **Aggiungi nuovo progetto** immettere **MSTest** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="637b4-112">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="637b4-113">Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.</span><span class="sxs-lookup"><span data-stu-id="637b4-113">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="637b4-114">Scegliere il modello **progetto di test MSTest (.NET Core)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="637b4-114">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="637b4-115">Nella pagina **Configura nuovo progetto** immettere **StringLibraryTest** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="637b4-115">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="637b4-116">Scegli quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="637b4-116">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="637b4-117">MSTest è uno dei tre Framework di test tra cui è possibile scegliere.</span><span class="sxs-lookup"><span data-stu-id="637b4-117">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="637b4-118">Gli altri sono xUnit e nUnit.</span><span class="sxs-lookup"><span data-stu-id="637b4-118">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="637b4-119">Visual Studio crea il progetto e apre il file di classe nella finestra del codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="637b4-119">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="637b4-120">Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="637b4-120">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   <span data-ttu-id="637b4-121">Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="637b4-121">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="637b4-122">Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.</span><span class="sxs-lookup"><span data-stu-id="637b4-122">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="637b4-123">Applica l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> alla classe `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="637b4-123">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="637b4-124">Applica l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo per definire `TestMethod1` in C# o `TestSub` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="637b4-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="637b4-125">Ogni metodo contrassegnato con [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in una classe di test contrassegnata con [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) viene eseguito automaticamente quando viene eseguito il unit test.</span><span class="sxs-lookup"><span data-stu-id="637b4-125">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="637b4-126">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **dipendenze** del progetto **StringLibraryTest** e scegliere **Aggiungi riferimento al progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="637b4-126">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="637b4-127">Nella finestra di dialogo **Gestione riferimenti** espandere il nodo **progetti** , quindi selezionare la casella accanto a **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="637b4-127">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="637b4-128">L'aggiunta di un riferimento all' `StringLibrary` assembly consente al compilatore di trovare i metodi **StringLibrary** durante la compilazione del progetto **StringLibraryTest** .</span><span class="sxs-lookup"><span data-stu-id="637b4-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="637b4-129">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="637b4-129">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="637b4-130">Aggiungere ed eseguire unit test metodi</span><span class="sxs-lookup"><span data-stu-id="637b4-130">Add and run unit test methods</span></span>

<span data-ttu-id="637b4-131">Quando Visual Studio esegue una unit test, viene eseguito ogni metodo contrassegnato con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attributo in una classe contrassegnata con l' <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="637b4-131">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="637b4-132">Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="637b4-132">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="637b4-133">I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="637b4-133">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="637b4-134">Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo.</span><span class="sxs-lookup"><span data-stu-id="637b4-134">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="637b4-135">`Assert`Nella tabella seguente sono illustrati alcuni dei metodi chiamati più di frequente della classe:</span><span class="sxs-lookup"><span data-stu-id="637b4-135">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="637b4-136">Metodi Assert</span><span class="sxs-lookup"><span data-stu-id="637b4-136">Assert methods</span></span>     | <span data-ttu-id="637b4-137">Funzione</span><span class="sxs-lookup"><span data-stu-id="637b4-137">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="637b4-138">Verifica che due oggetti o valori siano uguali.</span><span class="sxs-lookup"><span data-stu-id="637b4-138">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="637b4-139">L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="637b4-139">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="637b4-140">Verifica che due variabili oggetto facciano riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="637b4-140">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="637b4-141">Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="637b4-141">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="637b4-142">Verifica che una condizione sia `false`.</span><span class="sxs-lookup"><span data-stu-id="637b4-142">Verifies that a condition is `false`.</span></span> <span data-ttu-id="637b4-143">Il metodo ha esito negativo se la condizione è `true`.</span><span class="sxs-lookup"><span data-stu-id="637b4-143">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="637b4-144">Verifica che un oggetto non sia `null` .</span><span class="sxs-lookup"><span data-stu-id="637b4-144">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="637b4-145">Il metodo ha esito negativo se l'oggetto è `null`.</span><span class="sxs-lookup"><span data-stu-id="637b4-145">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="637b4-146">È anche possibile usare il <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodo in un metodo di test per indicare il tipo di eccezione che si prevede venga generata.</span><span class="sxs-lookup"><span data-stu-id="637b4-146">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="637b4-147">Il test ha esito negativo se l'eccezione specificata non viene generata.</span><span class="sxs-lookup"><span data-stu-id="637b4-147">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="637b4-148">Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="637b4-148">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="637b4-149">In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="637b4-149">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="637b4-150">Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="637b4-150">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="637b4-151">In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="637b4-151">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="637b4-152">Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca correttamente una [stringa vuota ( `String.Empty` )](xref:System.String.Empty), una stringa valida senza caratteri e il cui valore <xref:System.String.Length> è 0 e una `null` stringa che non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="637b4-152">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="637b4-153">Se `StartsWithUpper` viene chiamato come metodo di estensione su un' <xref:System.String> istanza, non può essere passato a una `null` stringa.</span><span class="sxs-lookup"><span data-stu-id="637b4-153">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="637b4-154">È tuttavia possibile chiamarlo direttamente come metodo statico e passarlo a un singolo argomento <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="637b4-154">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="637b4-155">Verranno definiti tre metodi, ognuno dei quali chiama <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> ripetutamente un metodo per ogni elemento in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="637b4-155">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="637b4-156">Poiché il metodo di test ha esito negativo non appena viene trovato il primo errore, verrà chiamato un overload del metodo che consente di passare una stringa che indica il valore stringa usato nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="637b4-156">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="637b4-157">Per creare i metodi di test:</span><span class="sxs-lookup"><span data-stu-id="637b4-157">To create the test methods:</span></span>

1. <span data-ttu-id="637b4-158">Nella finestra del codice *UnitTest1.cs* o *UnitTest1. vb* sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="637b4-158">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="637b4-159">Il test dei caratteri maiuscoli nel `TestStartsWithUpper` metodo include la lettera maiuscola greca Alpha (u + 0391) e la lettera maiuscola (u + maiuscola dell'alfabeto) cirillico.</span><span class="sxs-lookup"><span data-stu-id="637b4-159">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="637b4-160">Il test di caratteri minuscoli nel `TestDoesNotStartWithUpper` metodo include la piccola lettera greca alfa (u + 03B1) e la lettera minuscola cirillico ghe minuscola (u + 0433).</span><span class="sxs-lookup"><span data-stu-id="637b4-160">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="637b4-161">Nella barra dei menu selezionare **file**  >  **Salva UnitTest1.cs come** o **file**  >  **Salva UnitTest1. vb con nome**.</span><span class="sxs-lookup"><span data-stu-id="637b4-161">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="637b4-162">Nella finestra di dialogo **Salva file con nome** selezionare la freccia accanto al pulsante **Salva** e selezionare **Salva con codifica**.</span><span class="sxs-lookup"><span data-stu-id="637b4-162">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="637b4-163">![Finestra di dialogo Salva file con nome di Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="637b4-163">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="637b4-164">Nella finestra di dialogo **Conferma Salva con nome** selezionare il pulsante **Sì** per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="637b4-164">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="637b4-165">Nella finestra di dialogo **Opzioni di salvataggio avanzate** selezionare **Unicode (UTF-8 con firma digitale) - Tabella codici 65001** dall'elenco a discesa **Codifica** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="637b4-165">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="637b4-166">![Finestra di dialogo di Visual Studio Opzioni di salvataggio avanzate](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="637b4-166">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="637b4-167">Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII.</span><span class="sxs-lookup"><span data-stu-id="637b4-167">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="637b4-168">In tal caso, il runtime non decodifica accuratamente i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.</span><span class="sxs-lookup"><span data-stu-id="637b4-168">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="637b4-169">Sulla barra dei menu selezionare **test**  >  **Esegui tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="637b4-169">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="637b4-170">Se la finestra **Esplora test** non viene aperta, aprirla **scegliendo**  >  **Esplora test**test.</span><span class="sxs-lookup"><span data-stu-id="637b4-170">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="637b4-171">I tre test sono elencati nella sezione **Test superati** e nella sezione **Riepilogo** è riportato il risultato dell'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="637b4-171">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="637b4-172">![Finestra di Esplora test con i test riusciti](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="637b4-172">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="637b4-173">Gestione degli errori di test</span><span class="sxs-lookup"><span data-stu-id="637b4-173">Handle test failures</span></span>

<span data-ttu-id="637b4-174">Se si sta eseguendo lo sviluppo basato su test (TDD), si scrivono prima i test e hanno esito negativo la prima volta che vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="637b4-174">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="637b4-175">Si aggiunge quindi il codice all'app che rende il test riuscito.</span><span class="sxs-lookup"><span data-stu-id="637b4-175">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="637b4-176">In questo caso, il test è stato creato dopo la scrittura del codice dell'app che convalida, quindi non si è visto che il test non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="637b4-176">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="637b4-177">Per convalidare l'esito negativo di un test quando si prevede che abbia esito negativo, aggiungere un valore non valido all'input di test.</span><span class="sxs-lookup"><span data-stu-id="637b4-177">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="637b4-178">Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="637b4-178">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="637b4-179">Non è necessario salvare il file perché Visual Studio salva i file aperti automaticamente quando viene creata una soluzione per eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="637b4-179">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="637b4-180">Eseguire il test selezionando **test**  >  **Esegui tutti i test** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="637b4-180">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="637b4-181">La finestra **Esplora test** indica che due test hanno avuto esito positivo e uno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="637b4-181">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="637b4-182">![Finestra di Esplora test con i test non riusciti](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="637b4-182">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="637b4-183">Selezionare il test non superato `TestDoesNotStartWith` .</span><span class="sxs-lookup"><span data-stu-id="637b4-183">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="637b4-184">Nella finestra **Esplora test** viene visualizzato il messaggio generato dal metodo Assert: "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="637b4-184">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="637b4-185">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="637b4-185">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="637b4-186">A causa dell'errore, non sono state testate tutte le stringhe della matrice dopo l'errore.</span><span class="sxs-lookup"><span data-stu-id="637b4-186">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="637b4-187">![Finestra Esplora test che mostra l'errore di asserzione false](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="637b4-187">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="637b4-188">Annullare la modifica apportata nel passaggio 1 e rimuovere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="637b4-188">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="637b4-189">Eseguire di nuovo il test e i test superati.</span><span class="sxs-lookup"><span data-stu-id="637b4-189">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="637b4-190">Testare la versione di rilascio della libreria</span><span class="sxs-lookup"><span data-stu-id="637b4-190">Test the Release version of the library</span></span>

<span data-ttu-id="637b4-191">Ora che i test sono stati superati quando si esegue la versione di debug della libreria, eseguire i test per un ulteriore tempo rispetto alla build di rilascio della libreria.</span><span class="sxs-lookup"><span data-stu-id="637b4-191">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="637b4-192">Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.</span><span class="sxs-lookup"><span data-stu-id="637b4-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="637b4-193">Per testare la versione di rilascio, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="637b4-193">To test the Release build:</span></span>

1. <span data-ttu-id="637b4-194">Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="637b4-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="637b4-195">![Barra degli strumenti di Visual Studio con la configurazione di rilascio evidenziata](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="637b4-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="637b4-196">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **StringLibrary** e selezionare **Compila** dal menu di scelta rapida per ricompilare la libreria.</span><span class="sxs-lookup"><span data-stu-id="637b4-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="637b4-197">![Menu di scelta rapida StringLibrary con il comando di compilazione](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="637b4-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="637b4-198">Eseguire gli unit test scegliendo **test Esegui**  >  **tutti i test** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="637b4-198">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="637b4-199">I test avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="637b4-199">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="637b4-200">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="637b4-200">Additional resources</span></span>

- [<span data-ttu-id="637b4-201">Nozioni fondamentali sugli unit test di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="637b4-201">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)

## <a name="next-steps"></a><span data-ttu-id="637b4-202">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="637b4-202">Next steps</span></span>

<span data-ttu-id="637b4-203">In questa esercitazione è stata testata una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="637b4-203">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="637b4-204">Per rendere la libreria disponibile ad altri, è possibile pubblicarla in [NuGet](https://nuget.org) come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="637b4-204">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="637b4-205">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="637b4-205">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="637b4-206">Creare e pubblicare un pacchetto NuGet con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="637b4-206">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="637b4-207">Se si pubblica una libreria come pacchetto NuGet, altri utenti possono installarla e usarla.</span><span class="sxs-lookup"><span data-stu-id="637b4-207">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="637b4-208">Per informazioni su come seguire un'esercitazione su NuGet:</span><span class="sxs-lookup"><span data-stu-id="637b4-208">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="637b4-209">Installare e usare un pacchetto in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="637b4-209">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="637b4-210">Una libreria non deve essere distribuita come pacchetto.</span><span class="sxs-lookup"><span data-stu-id="637b4-210">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="637b4-211">Può essere incluso in un'app console che lo usa.</span><span class="sxs-lookup"><span data-stu-id="637b4-211">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="637b4-212">Per informazioni su come pubblicare un'app console, vedere l'esercitazione precedente in questa serie:</span><span class="sxs-lookup"><span data-stu-id="637b4-212">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="637b4-213">Pubblicare un'applicazione console .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="637b4-213">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
