---
title: Testare una libreria di classi .NET Standard con .NET Core in Visual StudioTest a .NET Standard class library with .NET Core in Visual Studio
description: Creare un progetto di unit test per la libreria di classi .NET Core. Verificare che la libreria di classi .NET Core funzioni correttamente con gli unit test.
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 307261088f5c7c69c0e69fbd6b99940c04842eec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156621"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="c413e-104">Testare una libreria .NET Standard con .NET Core in Visual StudioTest a .NET Standard library with .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c413e-104">Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="c413e-105">In [Compilare una libreria .NET Standard in Visual Studio](library-with-visual-studio.md)è stata <xref:System.String> creata una semplice libreria di classi che aggiunge un metodo di estensione alla classe .</span><span class="sxs-lookup"><span data-stu-id="c413e-105">In [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="c413e-106">Ora verrà creato uno unit test per verificare che tale libreria funzioni nel modo previsto.</span><span class="sxs-lookup"><span data-stu-id="c413e-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="c413e-107">Il progetto unit test verrà aggiunto alla soluzione creata nell'articolo precedente.</span><span class="sxs-lookup"><span data-stu-id="c413e-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="c413e-108">Creare un progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="c413e-108">Create a unit test project</span></span>

<span data-ttu-id="c413e-109">Per creare un progetto unit test, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c413e-109">To create the unit test project, do the following:</span></span>

1. <span data-ttu-id="c413e-110">Aprire `ClassLibraryProjects` la soluzione creata nell'articolo [Compilare una libreria .NET Standard in Visual Studio.Open](library-with-visual-studio.md) the solution you created in the Build a .NET Standard library in Visual Studio article.</span><span class="sxs-lookup"><span data-stu-id="c413e-110">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="c413e-111">Aggiungere un nuovo progetto di unit test denominato "StringLibraryTest" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="c413e-111">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="c413e-112">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="c413e-112">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="c413e-113">Nella pagina **Aggiungi un nuovo progetto** immettere **mstest** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c413e-113">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="c413e-114">Scegliere **C '** o Visual **Basic** dall'elenco linguaggio e quindi scegliere Tutte **le piattaforme** dall'elenco Piattaforma .</span><span class="sxs-lookup"><span data-stu-id="c413e-114">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c413e-115">Scegliere il modello **MsTest Test Project (.NET Core)** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c413e-115">Choose the **MsTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="c413e-116">Nella pagina **Configura il nuovo progetto** immettere **StringLibraryTest** nella casella **Nome progetto.**</span><span class="sxs-lookup"><span data-stu-id="c413e-116">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="c413e-117">quindi scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c413e-117">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c413e-118">Oltre a MSTest, è anche possibile creare progetti di test xUnit e nUnit per .NET Core in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c413e-118">In addition to an MSTest, you can also create xUnit and nUnit test projects for .NET Core in Visual Studio.</span></span>

1. <span data-ttu-id="c413e-119">Visual Studio crea il progetto e apre il file di classe nella finestra del codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c413e-119">Visual Studio creates the project and opens the class file in the code window with the following code:</span></span>

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

   <span data-ttu-id="c413e-120">Il codice sorgente creato dal modello di unit test esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c413e-120">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="c413e-121">Importa lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, contenente i tipi usati per il testing unità.</span><span class="sxs-lookup"><span data-stu-id="c413e-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="c413e-122">Applica l'attributo [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) alla classe `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="c413e-122">It applies the [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="c413e-123">Ogni metodo di test presente in una classe di test contrassegnata con l'attributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) viene eseguito automaticamente durante l'esecuzione dello unit test.</span><span class="sxs-lookup"><span data-stu-id="c413e-123">Each test method in a test class tagged with the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="c413e-124">Applica l'attributo [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) da `TestMethod1` `TestSub` definire in C, o in Visual Basic come metodo di test per l'esecuzione automatica quando viene eseguito lo unit test.</span><span class="sxs-lookup"><span data-stu-id="c413e-124">It applies the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="c413e-125">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto **StringLibraryTest** e selezionare **Aggiungi riferimento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="c413e-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-126">![Menu di scelta rapida delle dipendenze StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-126">![Context menu of StringLibraryTest dependencies](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span></span>

1. <span data-ttu-id="c413e-127">Nella finestra di dialogo **Gestione riferimenti** espandere il nodo **Progetti** e selezionare la casella accanto a **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="c413e-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="c413e-128">L'aggiunta di un riferimento all'assembly `StringLibrary` consente al compilatore di individuare i metodi **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="c413e-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="c413e-129">Selezionare il pulsante **OK.**</span><span class="sxs-lookup"><span data-stu-id="c413e-129">Select the **OK** button.</span></span> <span data-ttu-id="c413e-130">Un riferimento viene aggiunto al `StringLibrary`progetto di libreria di classi, .</span><span class="sxs-lookup"><span data-stu-id="c413e-130">A reference is added to your class library project, `StringLibrary`.</span></span>

   ![Finestra di dialogo Gestione riferimenti in Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="c413e-132">Aggiungere ed eseguire metodi di unit test</span><span class="sxs-lookup"><span data-stu-id="c413e-132">Add and run unit test methods</span></span>

<span data-ttu-id="c413e-133">Quando Visual Studio esegue uno unit test, esegue ogni <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> metodo contrassegnato con l'attributo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> in una classe di unit test, la classe a cui viene applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="c413e-133">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="c413e-134">Un metodo di test termina quando viene rilevato il primo errore o quando tutti i test contenuti nel metodo hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c413e-134">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="c413e-135">I test più comuni chiamano i membri della classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="c413e-135">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="c413e-136">Molti metodi assert includono almeno due parametri, uno dei quali corrisponde al risultato previsto del test, mentre l'altro corrisponde al risultato effettivo.</span><span class="sxs-lookup"><span data-stu-id="c413e-136">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="c413e-137">Nella tabella `Assert` seguente sono riportati alcuni dei metodi chiamati più di frequente dalla classe:</span><span class="sxs-lookup"><span data-stu-id="c413e-137">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="c413e-138">Metodi Assert</span><span class="sxs-lookup"><span data-stu-id="c413e-138">Assert methods</span></span>     | <span data-ttu-id="c413e-139">Funzione</span><span class="sxs-lookup"><span data-stu-id="c413e-139">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="c413e-140">Verifica che due oggetti o valori siano uguali.</span><span class="sxs-lookup"><span data-stu-id="c413e-140">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="c413e-141">L'asserzione ha esito negativo se i valori o gli oggetti non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="c413e-141">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="c413e-142">Verifica che due variabili oggetto facciano riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="c413e-142">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="c413e-143">Il metodo ha esito negativo se le variabili fanno riferimento a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="c413e-143">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="c413e-144">Verifica che una condizione sia `false`.</span><span class="sxs-lookup"><span data-stu-id="c413e-144">Verifies that a condition is `false`.</span></span> <span data-ttu-id="c413e-145">Il metodo ha esito negativo se la condizione è `true`.</span><span class="sxs-lookup"><span data-stu-id="c413e-145">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="c413e-146">Verifica che un oggetto non `null`sia .</span><span class="sxs-lookup"><span data-stu-id="c413e-146">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="c413e-147">Il metodo ha esito negativo se l'oggetto è `null`.</span><span class="sxs-lookup"><span data-stu-id="c413e-147">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="c413e-148">È inoltre possibile <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> utilizzare il metodo in un metodo di test per indicare il tipo di eccezione che deve generare.</span><span class="sxs-lookup"><span data-stu-id="c413e-148">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="c413e-149">Il test ha esito negativo se non viene generata l'eccezione specificata.</span><span class="sxs-lookup"><span data-stu-id="c413e-149">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="c413e-150">Durante il test del metodo `StringLibrary.StartsWithUpper`, è possibile specificare alcune stringhe che iniziano con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="c413e-150">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="c413e-151">In tal caso si prevede che il metodo restituisca `true`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>.</span><span class="sxs-lookup"><span data-stu-id="c413e-151">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="c413e-152">Analogamente, è possibile specificare alcune stringhe che iniziano con un valore diverso da un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="c413e-152">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="c413e-153">In tal caso si prevede che il metodo restituisca `false`, quindi è possibile chiamare il metodo <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.</span><span class="sxs-lookup"><span data-stu-id="c413e-153">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="c413e-154">Poiché il metodo della libreria gestisce le stringhe, è anche necessario assicurarsi che gestisca <xref:System.String.Length> correttamente una `null` stringa [vuota (`String.Empty`)](xref:System.String.Empty), una stringa valida che non contiene caratteri e la cui valore 0 e una stringa che non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="c413e-154">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="c413e-155">Se `StartsWithUpper` viene chiamato come metodo <xref:System.String> di estensione in un'istanza, non può essere passata una `null` stringa.</span><span class="sxs-lookup"><span data-stu-id="c413e-155">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="c413e-156">È tuttavia possibile chiamarlo direttamente come metodo statico e passarlo a un singolo argomento <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c413e-156">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="c413e-157">Si definiranno tre metodi, ognuno dei quali chiama ripetutamente un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> metodo per ogni elemento in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="c413e-157">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="c413e-158">Poiché il metodo di test ha esito negativo non appena viene trovato il primo errore, verrà chiamato un overload del metodo che consente di passare una stringa che indica il valore stringa utilizzato nella chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="c413e-158">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="c413e-159">Per creare i metodi di test:</span><span class="sxs-lookup"><span data-stu-id="c413e-159">To create the test methods:</span></span>

1. <span data-ttu-id="c413e-160">Nella finestra del codice *UnitTest1.cs* o *UnitTest1.vb* sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c413e-160">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="c413e-161">Il test dei caratteri `TestStartsWithUpper` maiuscoli nel metodo include la lettera maiuscola greca alfa (U-0391) e la lettera maiuscola cirillica EM (U-041C).</span><span class="sxs-lookup"><span data-stu-id="c413e-161">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="c413e-162">Il test dei caratteri `TestDoesNotStartWithUpper` minuscoli nel metodo include la lettera piccola greca alfa (U-03B1) e la lettera piccola cirillica Ghe (U-0433).</span><span class="sxs-lookup"><span data-stu-id="c413e-162">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="c413e-163">Sulla barra dei menu selezionare **Salva file** > **UnitTest1.cs con nome** o Salva **file** > **UnitTest1.vb con nome**.</span><span class="sxs-lookup"><span data-stu-id="c413e-163">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="c413e-164">Nella finestra di dialogo **Salva file con nome** selezionare la freccia accanto al pulsante **Salva** e selezionare **Salva con codifica**.</span><span class="sxs-lookup"><span data-stu-id="c413e-164">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-165">![Finestra di dialogo Salva file con nome di Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-165">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="c413e-166">Nella finestra di dialogo **Conferma Salva con nome** selezionare il pulsante **Sì** per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="c413e-166">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="c413e-167">Nella finestra di dialogo **Opzioni di salvataggio avanzate** selezionare **Unicode (UTF-8 con firma digitale) - Tabella codici 65001** dall'elenco a discesa **Codifica** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="c413e-167">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-168">![Finestra di dialogo di Visual Studio Opzioni di salvataggio avanzate](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-168">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="c413e-169">Se il salvataggio del codice sorgente come file con codifica UTF8 ha esito negativo, Visual Studio può salvarlo come file ASCII.</span><span class="sxs-lookup"><span data-stu-id="c413e-169">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="c413e-170">In questo caso, il runtime non decodifica con precisione i caratteri UTF8 al di fuori dell'intervallo ASCII e i risultati del test non saranno corretti.</span><span class="sxs-lookup"><span data-stu-id="c413e-170">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="c413e-171">Sulla barra dei menu selezionare**Esecuzione** >  **dei test** > **di tutti i test**.</span><span class="sxs-lookup"><span data-stu-id="c413e-171">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="c413e-172">Viene aperta la finestra **Esplora test** che illustra che i test sono stati eseguiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="c413e-172">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="c413e-173">I tre test sono elencati nella sezione **Test superati** e nella sezione **Riepilogo** è riportato il risultato dell'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="c413e-173">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-174">![Finestra di Esplora test con i test riusciti](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-174">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="c413e-175">Gestire gli errori di test</span><span class="sxs-lookup"><span data-stu-id="c413e-175">Handle test failures</span></span>

<span data-ttu-id="c413e-176">L'esecuzione dei test non ha generato errori ma è opportuno apportare qualche modifica in modo che uno dei metodi di test abbia esito negativo:</span><span class="sxs-lookup"><span data-stu-id="c413e-176">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="c413e-177">Modificare la matrice `words` del metodo `TestDoesNotStartWithUpper` per includere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="c413e-177">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="c413e-178">Non è necessario salvare il file perché Visual Studio salva i file aperti automaticamente quando viene creata una soluzione per eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="c413e-178">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="c413e-179">Eseguire il test selezionando**Esecuzione** >  **dei test** > **tutti i test** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="c413e-179">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="c413e-180">La finestra **Esplora test** indica che due test hanno avuto esito positivo e uno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c413e-180">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-181">![Finestra di Esplora test con i test non riusciti](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-181">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="c413e-182">Selezionare il `TestDoesNotStartWith`test non riuscito, .</span><span class="sxs-lookup"><span data-stu-id="c413e-182">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="c413e-183">Nella finestra **Esplora test** viene visualizzato il messaggio generato dal metodo Assert: "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="c413e-183">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="c413e-184">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="c413e-184">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="c413e-185">A causa dell'errore, tutte le stringhe nella matrice dopo "Errore" non sono state testate.</span><span class="sxs-lookup"><span data-stu-id="c413e-185">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-186">![Finestra Esplora test con l'errore di asserzione IsFalse](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-186">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="c413e-187">Annullare la modifica apportata nel passaggio 1 e rimuovere la stringa "Error".</span><span class="sxs-lookup"><span data-stu-id="c413e-187">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="c413e-188">Eseguire nuovamente il test. I test verranno superati.</span><span class="sxs-lookup"><span data-stu-id="c413e-188">Rerun the test and the tests will pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="c413e-189">Testare la versione finale della libreria</span><span class="sxs-lookup"><span data-stu-id="c413e-189">Test the Release version of the library</span></span>

<span data-ttu-id="c413e-190">I test sono stati eseguiti con la versione di debug della libreria.</span><span class="sxs-lookup"><span data-stu-id="c413e-190">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="c413e-191">Dopo che tutti i test sono stati superati e la libreria è stata testata in modo adeguato, è necessario ripetere i test con la versione di rilascio della libreria stessa.</span><span class="sxs-lookup"><span data-stu-id="c413e-191">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="c413e-192">Esistono infatti alcuni fattori, ad esempio le ottimizzazioni del compilatore, in grado di generare a volte comportamenti diversi tra la versione di debug e quella di rilascio.</span><span class="sxs-lookup"><span data-stu-id="c413e-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="c413e-193">Per testare la versione di rilascio, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c413e-193">To test the Release build:</span></span>

1. <span data-ttu-id="c413e-194">Nella barra degli strumenti di Visual Studio modificare la configurazione di compilazione da **Debug** a **Rilascio**.</span><span class="sxs-lookup"><span data-stu-id="c413e-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-195">![Barra degli strumenti di Visual Studio con la configurazione di rilascio evidenziata](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="c413e-196">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **StringLibrary** e selezionare **Compila** dal menu di scelta rapida per ricompilare la libreria.</span><span class="sxs-lookup"><span data-stu-id="c413e-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c413e-197">![Menu di scelta rapida StringLibrary con il comando di compilazione](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="c413e-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="c413e-198">Eseguire gli unit test scegliendo**Esecuzione** >  **dei test** > **tutti i test** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="c413e-198">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="c413e-199">I test avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c413e-199">The tests pass.</span></span>

<span data-ttu-id="c413e-200">Dopo aver completato le operazioni di test della libreria, il passaggio successivo consiste nel rendere quest'ultima disponibile ai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="c413e-200">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="c413e-201">È possibile aggregarla a una o più applicazioni oppure è possibile distribuirla come pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="c413e-201">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="c413e-202">Per altre informazioni, vedere [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md) (Utilizzo di una libreria di classi .NET Standard).</span><span class="sxs-lookup"><span data-stu-id="c413e-202">For more information, see [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c413e-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c413e-203">See also</span></span>

- [<span data-ttu-id="c413e-204">Nozioni di base su unit test - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c413e-204">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
