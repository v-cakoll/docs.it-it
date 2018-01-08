---
title: Compilazione di una libreria di classi con Visual Basic e .NET Core in Visual Studio 2017
description: Informazioni su come creare una libreria di classi scritta in Visual Basic usando Visual Studio 2017
keywords: .NET Core, libreria di classi .NET Standard, Visual Studio 2017, Visual Basic
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
dev_langs: vb
ms.workload: dotnetcore
ms.openlocfilehash: b8d87e3a97e2ffeb8e8712bfa5d178bb855f402d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="building-a-class-library-with-visual-basic-and-net-core-in-visual-studio-2017"></a><span data-ttu-id="8e998-104">Compilazione di una libreria di classi con Visual Basic e .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8e998-104">Building a class library with Visual Basic and .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="8e998-105">La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e998-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="8e998-106">Una libreria di classi che esegue la destinazione a .NET Standard 2.0 consente la chiamata alla libreria da qualsiasi implementazione di .NET che supporti questa versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="8e998-106">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="8e998-107">Dopo aver completato la libreria di classi, è possibile decidere se si vuole distribuirla come componente di terze parti o se si vuole includerla come componente in bundle con una o più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8e998-107">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="8e998-108">Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="8e998-108">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="8e998-109">In questo argomento si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe,</span><span class="sxs-lookup"><span data-stu-id="8e998-109">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="8e998-110">che verrà implementato come [metodo di estensione](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md), in modo da poter essere chiamato come se fosse un membro della classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="8e998-110">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="8e998-111">Creazione di una soluzione per la libreria di classi</span><span class="sxs-lookup"><span data-stu-id="8e998-111">Creating a class library solution</span></span>

<span data-ttu-id="8e998-112">Iniziare creando una soluzione per il progetto di libreria di classi e per i progetti correlati.</span><span class="sxs-lookup"><span data-stu-id="8e998-112">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="8e998-113">Una soluzione Visual Studio funge solo da contenitore per uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="8e998-113">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="8e998-114">Per creare la soluzione:</span><span class="sxs-lookup"><span data-stu-id="8e998-114">To create the solution:</span></span>

1. <span data-ttu-id="8e998-115">Nella barra dei menu di Visual Studio scegliere **File** > **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="8e998-115">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="8e998-116">Nella finestra di dialogo **Nuovo progetto** espandere il nodo **Altri tipi di progetti** e selezionare **Soluzioni di Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="8e998-116">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="8e998-117">Assegnare alla soluzione il nome "ClassLibraryProjects" e selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e998-117">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Finestra di dialogo Nuovo progetto](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="8e998-119">Creazione del progetto di libreria di classi</span><span class="sxs-lookup"><span data-stu-id="8e998-119">Creating the class library project</span></span>

<span data-ttu-id="8e998-120">Creare un progetto di libreria di classi:</span><span class="sxs-lookup"><span data-stu-id="8e998-120">Create your class library project:</span></span>

1. <span data-ttu-id="8e998-121">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file della soluzione **ClassLibraryProjects** e dal menu di scelta rapida selezionare **Aggiungi** > **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="8e998-121">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="8e998-122">Nella finestra di dialogo **Aggiungi nuovo progetto** espandere il nodo **Visual Basic**, quindi selezionare il nodo **.NET Standard** seguito dal modello di progetto **Libreria di classi (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="8e998-122">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="8e998-123">Nella casella di testo **Nome** immettere "StringLibrary" come nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="8e998-123">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="8e998-124">Scegliere **OK** per creare il progetto di libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="8e998-124">Select **OK** to create the class library project.</span></span>

   ![Finestra di dialogo Aggiungi nuovo progetto](./media/vb-library-with-visual-studio/libproject.png)

   <span data-ttu-id="8e998-126">La finestra di codice viene quindi aperta nell'ambiente di sviluppo di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8e998-126">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![Finestra dell'applicazione di Visual Studio che illustra il codice del modello della libreria di classi predefinito](./media/vb-library-with-visual-studio/stringlibrary.png)

1. <span data-ttu-id="8e998-128">Assicurarsi che sia stata eseguita la destinazione della libreria alla versione corretta di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="8e998-128">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="8e998-129">Fare clic con il pulsante destro del mouse sul progetto libreria nelle finestre di **Esplora soluzioni**, quindi selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8e998-129">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="8e998-130">La casella di testo **Framework di destinazione** indica che si sta eseguendo la destinazione a .NET 2.0 Standard.</span><span class="sxs-lookup"><span data-stu-id="8e998-130">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/properties.png)

1. <span data-ttu-id="8e998-132">Inoltre, nella finestra di dialogo **Proprietà** cancellare il testo nella casella di testo **Spazio dei nomi radice**.</span><span class="sxs-lookup"><span data-stu-id="8e998-132">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="8e998-133">Per ogni progetto, Visual Basic crea automaticamente uno spazio dei nomi che corrisponde al nome del progetto e gli spazi dei nomi definiti nel file di codice sorgente sono gli elementi padre di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8e998-133">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="8e998-134">Si desidera definire uno spazio dei nomi di livello superiore usando la parola chiave [`namespace` ](../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8e998-134">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="8e998-135">Nella finestra del codice sostituire il codice con il seguente:</span><span class="sxs-lookup"><span data-stu-id="8e998-135">Replace the code in the code window with the following code and save the file:</span></span>

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="8e998-136">La libreria di classi `UtilityLibraries.StringLibrary` contiene un metodo denominato `StartsWithUpper`, che restituisce un valore <xref:System.Boolean> che indica se l'istanza della stringa corrente inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="8e998-136">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="8e998-137">Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli.</span><span class="sxs-lookup"><span data-stu-id="8e998-137">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="8e998-138">Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="8e998-138">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="8e998-139">Nella barra dei menu selezionare **Compila** > **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="8e998-139">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="8e998-140">Il progetto dovrebbe essere compilato senza errori.</span><span class="sxs-lookup"><span data-stu-id="8e998-140">The project should compile without error.</span></span>

   ![Riquadro di output che illustra che la compilazione ha avuto esito positivo](./media/library-with-visual-studio/buildsucceeds.png)



## <a name="next-step"></a><span data-ttu-id="8e998-142">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8e998-142">Next step</span></span>

<span data-ttu-id="8e998-143">La compilazione della libreria è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8e998-143">You've successfully built the library.</span></span> <span data-ttu-id="8e998-144">Non è tuttavia possibile sapere se funziona come previsto poiché non è stato ancora chiamato uno dei metodi.</span><span class="sxs-lookup"><span data-stu-id="8e998-144">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="8e998-145">Il passaggio successivo per lo sviluppo della libreria consiste nel testarla usando un [Progetto unit test](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8e998-145">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>
