---
title: Creare una libreria di classi .NET Standard in Visual StudioBuild a .NET Standard class library in Visual Studio
description: Informazioni su come compilare una libreria di classi .NET Standard scritta in Visual Basic o in Visual Basic utilizzando Visual Studio
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714013"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="6301e-103">Creare una libreria .NET Standard in Visual StudioBuild a .NET Standard library in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6301e-103">Build a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="6301e-104">La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6301e-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="6301e-105">Una libreria di classi destinata a .NET Standard 2.0 consente di chiamare la libreria da qualsiasi implementazione di .NET che supporta tale versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6301e-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="6301e-106">Dopo aver completato la libreria di classi, è possibile decidere se si vuole distribuirla come componente di terze parti o se si vuole includerla come componente in bundle con una o più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6301e-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="6301e-107">Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="6301e-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="6301e-108">In questo argomento si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe,</span><span class="sxs-lookup"><span data-stu-id="6301e-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="6301e-109">che verrà implementato come [metodo di estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md), in modo da poter essere chiamato come se fosse un membro della classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6301e-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="6301e-110">Creare una soluzione di Visual StudioCreate a Visual Studio solution</span><span class="sxs-lookup"><span data-stu-id="6301e-110">Create a Visual Studio solution</span></span>

<span data-ttu-id="6301e-111">Iniziare creando una soluzione vuota per inserire il progetto di libreria di classi in.</span><span class="sxs-lookup"><span data-stu-id="6301e-111">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="6301e-112">Una soluzione di Visual Studio funge da contenitore per uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="6301e-112">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="6301e-113">Si aggiungeranno altri progetti correlati alla stessa soluzione se si continua con la serie di esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="6301e-113">You'll add additional, related projects to the same solution if you continue on with the tutorial series.</span></span>

<span data-ttu-id="6301e-114">Per creare la soluzione vuota:</span><span class="sxs-lookup"><span data-stu-id="6301e-114">To create the blank solution:</span></span>

1. <span data-ttu-id="6301e-115">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6301e-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="6301e-116">Nella finestra di avvio scegliere **Crea un nuovo progetto.**</span><span class="sxs-lookup"><span data-stu-id="6301e-116">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="6301e-117">Nella pagina **Crea un nuovo progetto** immettere la **soluzione** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="6301e-117">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="6301e-118">Scegliere il modello **Soluzione vuota** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6301e-118">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Modello Soluzione vuota in Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="6301e-120">Nella pagina **Configura il nuovo progetto** immettere **ClassLibraryProjects** nella casella **Nome progetto.**</span><span class="sxs-lookup"><span data-stu-id="6301e-120">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="6301e-121">Scegliere quindi **Crea,** quindi Crea .</span><span class="sxs-lookup"><span data-stu-id="6301e-121">Then, choose **Create**.</span></span>

> [!TIP]
> <span data-ttu-id="6301e-122">È anche possibile ignorare questo passaggio e consentire a Visual Studio di creare automaticamente la soluzione quando si crea il progetto nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="6301e-122">You can also skip this step and let Visual Studio create the solution for you when you create the project in the next step.</span></span> <span data-ttu-id="6301e-123">Cercare le opzioni della soluzione nella pagina **Configura il nuovo progetto.**</span><span class="sxs-lookup"><span data-stu-id="6301e-123">Look for the solution options on the **Configure your new project** page.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="6301e-124">Creare un progetto di libreria di classi</span><span class="sxs-lookup"><span data-stu-id="6301e-124">Create a class library project</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="6301e-125">C #</span><span class="sxs-lookup"><span data-stu-id="6301e-125">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="6301e-126">Aggiungere alla soluzione un nuovo progetto di libreria di classi .NET Standard di C.NET denominato "StringLibrary".</span><span class="sxs-lookup"><span data-stu-id="6301e-126">Add a new C# .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="6301e-127">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="6301e-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="6301e-128">Nella pagina **Aggiungi un nuovo progetto** immettere la **raccolta** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="6301e-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="6301e-129">Scegliere **C 'c'è** dall'elenco linguaggio e quindi scegliere **Tutte le piattaforme** dall'elenco piattaforma .</span><span class="sxs-lookup"><span data-stu-id="6301e-129">Choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="6301e-130">Scegliere il modello Libreria di classi **(.NET Standard)** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6301e-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="6301e-131">Nella pagina **Configura il nuovo progetto** immettere **StringLibrary** nella casella **Nome progetto.**</span><span class="sxs-lookup"><span data-stu-id="6301e-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="6301e-132">Scegliere quindi **Crea,** quindi Crea .</span><span class="sxs-lookup"><span data-stu-id="6301e-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="6301e-133">Verificare che la libreria sia destinata alla versione corretta di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6301e-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="6301e-134">Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6301e-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="6301e-135">La casella di testo Framework di destinazione indica che il progetto è destinato a .NET Standard 2.0.The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="6301e-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="6301e-137">Nella finestra del codice sostituire il codice con il seguente:</span><span class="sxs-lookup"><span data-stu-id="6301e-137">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="6301e-138">La libreria `UtilityLibraries.StringLibrary`di classi , `StartsWithUpper`, contiene un metodo denominato .</span><span class="sxs-lookup"><span data-stu-id="6301e-138">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="6301e-139">Questo metodo <xref:System.Boolean> restituisce un valore che indica se l'istanza della stringa corrente inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="6301e-139">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="6301e-140">Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli.</span><span class="sxs-lookup"><span data-stu-id="6301e-140">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="6301e-141">Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="6301e-141">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="6301e-142">Nella barra dei menu selezionare **Compila** > **soluzione**.</span><span class="sxs-lookup"><span data-stu-id="6301e-142">On the menu bar, select **Build** > **Build Solution**.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="6301e-143">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6301e-143">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="6301e-144">Aggiungere alla soluzione un nuovo progetto di libreria di classi Visual Basic .NET Standard denominato "StringLibrary".</span><span class="sxs-lookup"><span data-stu-id="6301e-144">Add a new Visual Basic .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="6301e-145">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="6301e-145">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="6301e-146">Nella pagina **Aggiungi un nuovo progetto** immettere la **raccolta** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="6301e-146">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="6301e-147">Scegliere **Visual Basic** dall'elenco Linguaggio, quindi scegliere Tutte le **piattaforme** dall'elenco Piattaforma.</span><span class="sxs-lookup"><span data-stu-id="6301e-147">Choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="6301e-148">Scegliere il modello Libreria di classi **(.NET Standard)** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6301e-148">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="6301e-149">Nella pagina **Configura il nuovo progetto** immettere **StringLibrary** nella casella **Nome progetto.**</span><span class="sxs-lookup"><span data-stu-id="6301e-149">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="6301e-150">Scegliere quindi **Crea,** quindi Crea .</span><span class="sxs-lookup"><span data-stu-id="6301e-150">Then, choose **Create**.</span></span>

1. <span data-ttu-id="6301e-151">Verificare che la libreria sia destinata alla versione corretta di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6301e-151">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="6301e-152">Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6301e-152">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="6301e-153">La casella di testo Framework di destinazione indica che il progetto è destinato a .NET Standard 2.0.The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="6301e-153">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/vb/library-project-properties.png)

1. <span data-ttu-id="6301e-155">Nella finestra di dialogo **Proprietà** cancellare il testo nella casella di testo **Spazio dei nomi radice.**</span><span class="sxs-lookup"><span data-stu-id="6301e-155">In the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="6301e-156">Per ogni progetto, Visual Basic crea automaticamente uno spazio dei nomi che corrisponde al nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="6301e-156">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="6301e-157">In questa esercitazione si definisce uno [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) spazio dei nomi di primo livello usando la parola chiave nel file di codice.</span><span class="sxs-lookup"><span data-stu-id="6301e-157">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="6301e-158">Nella finestra del codice sostituire il codice con il seguente:</span><span class="sxs-lookup"><span data-stu-id="6301e-158">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="6301e-159">La libreria `UtilityLibraries.StringLibrary`di classi , `StartsWithUpper`, contiene un metodo denominato .</span><span class="sxs-lookup"><span data-stu-id="6301e-159">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="6301e-160">Questo metodo <xref:System.Boolean> restituisce un valore che indica se l'istanza della stringa corrente inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="6301e-160">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="6301e-161">Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli.</span><span class="sxs-lookup"><span data-stu-id="6301e-161">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="6301e-162">Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="6301e-162">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="6301e-163">Nella barra dei menu selezionare **Compila** > **soluzione**.</span><span class="sxs-lookup"><span data-stu-id="6301e-163">On the menu bar, select **Build** > **Build Solution**.</span></span>

---

   <span data-ttu-id="6301e-164">Il progetto dovrebbe essere compilato senza errori.</span><span class="sxs-lookup"><span data-stu-id="6301e-164">The project should compile without error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6301e-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6301e-165">Next steps</span></span>

<span data-ttu-id="6301e-166">La compilazione della libreria è stata completata.</span><span class="sxs-lookup"><span data-stu-id="6301e-166">You've successfully built the library.</span></span> <span data-ttu-id="6301e-167">Non è tuttavia possibile sapere se funziona come previsto poiché non è stato ancora chiamato uno dei metodi.</span><span class="sxs-lookup"><span data-stu-id="6301e-167">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="6301e-168">Il passaggio successivo nello sviluppo della libreria consiste nel testarla.</span><span class="sxs-lookup"><span data-stu-id="6301e-168">The next step in developing your library is to test it.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6301e-169">Creare un progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="6301e-169">Create a unit test project</span></span>](testing-library-with-visual-studio.md)
