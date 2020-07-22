---
title: Come usare argomenti denominati e facoltativi nella programmazione di Office-Guida per programmatori C#
description: Informazioni su come usare argomenti denominati e argomenti facoltativi per facilitare l'accesso alle interfacce COM, ad esempio le API di automazione Microsoft Office.
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 7e24331d37e8fdbe2bc66a2d9f73a5f6a7242af9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864345"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="fa1ff-103">Come usare argomenti denominati e facoltativi nella programmazione di Office (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="fa1ff-103">How to use named and optional arguments in Office programming (C# Programming Guide)</span></span>

<span data-ttu-id="fa1ff-104">Gli argomenti denominati e gli argomenti facoltativi, introdotti in C# 4, migliorano la praticità, la flessibilità e la leggibilità nella programmazione C#.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-104">Named arguments and optional arguments, introduced in C# 4, enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="fa1ff-105">Queste funzionalità, poi, semplificano notevolmente l'accesso alle interfacce COM, quali le API di automazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-105">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>

<span data-ttu-id="fa1ff-106">Nell'esempio seguente, il metodo [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) dispone di sedici parametri che rappresentano le caratteristiche di una tabella, ad esempio il numero di colonne e di righe, la formattazione, i bordi, i tipi di carattere e i colori.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-106">In the following example, method [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="fa1ff-107">I sedici parametri sono tutti facoltativi, perché nella maggior parte dei casi non si vogliono specificare particolari valori per tutti.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-107">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="fa1ff-108">Senza gli argomenti denominati e facoltativi, tuttavia, è necessario specificare un valore o un valore di segnaposto per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-108">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="fa1ff-109">Con gli argomenti denominati e facoltativi si specificano valori solo per i parametri obbligatori per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-109">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>

<span data-ttu-id="fa1ff-110">Per eseguire queste procedure, Microsoft Office Word deve essere installato.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-110">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a><span data-ttu-id="fa1ff-111">Per creare un nuovo progetto di applicazione console</span><span class="sxs-lookup"><span data-stu-id="fa1ff-111">To create a new console application</span></span>

1. <span data-ttu-id="fa1ff-112">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-112">Start Visual Studio.</span></span>

2. <span data-ttu-id="fa1ff-113">Scegliere **Nuovo** dal menu **File**e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-113">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="fa1ff-114">Nel riquadro **Categorie di modelli** espandere **Visual C#** e quindi fare clic su **Windows**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-114">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>

4. <span data-ttu-id="fa1ff-115">Verificare che nella parte superiore del riquadro **Modelli** sia visualizzato **.NET Framework 4** nella casella **Framework di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-115">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>

5. <span data-ttu-id="fa1ff-116">Nel riquadro **Modelli** fare clic su **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-116">In the **Templates** pane, click **Console Application**.</span></span>

6. <span data-ttu-id="fa1ff-117">Digitare un nome per il progetto nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-117">Type a name for your project in the **Name** field.</span></span>

7. <span data-ttu-id="fa1ff-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-118">Click **OK**.</span></span>

     <span data-ttu-id="fa1ff-119">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-119">The new project appears in **Solution Explorer**.</span></span>

## <a name="to-add-a-reference"></a><span data-ttu-id="fa1ff-120">Per aggiungere un riferimento</span><span class="sxs-lookup"><span data-stu-id="fa1ff-120">To add a reference</span></span>

1. <span data-ttu-id="fa1ff-121">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nome del progetto e quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-121">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="fa1ff-122">Verrà visualizzata la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-122">The **Add Reference** dialog box appears.</span></span>

2. <span data-ttu-id="fa1ff-123">Nella pagina **.NET** selezionare **Microsoft.Office.Interop.Word** nell'elenco **Nome componente**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-123">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>

3. <span data-ttu-id="fa1ff-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-124">Click **OK**.</span></span>

## <a name="to-add-necessary-using-directives"></a><span data-ttu-id="fa1ff-125">Per aggiungere le direttive using necessarie</span><span class="sxs-lookup"><span data-stu-id="fa1ff-125">To add necessary using directives</span></span>

1. <span data-ttu-id="fa1ff-126">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file *Program.cs* e quindi fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-126">In **Solution Explorer**, right-click the *Program.cs* file and then click **View Code**.</span></span>

2. <span data-ttu-id="fa1ff-127">Aggiungere le seguenti `using` direttive all'inizio del file di codice:</span><span class="sxs-lookup"><span data-stu-id="fa1ff-127">Add the following `using` directives to the top of the code file:</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#4)]

## <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="fa1ff-128">Per visualizzare il testo in un documento di Word</span><span class="sxs-lookup"><span data-stu-id="fa1ff-128">To display text in a Word document</span></span>

1. <span data-ttu-id="fa1ff-129">Nella `Program` classe in *Program.cs*aggiungere il metodo seguente per creare un'applicazione di Word e un documento di Word.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-129">In the `Program` class in *Program.cs*, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="fa1ff-130">Il metodo [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) dispone di quattro parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-130">The [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) method has four optional parameters.</span></span> <span data-ttu-id="fa1ff-131">Questo esempio usa i relativi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-131">This example uses their default values.</span></span> <span data-ttu-id="fa1ff-132">Non sono pertanto necessari argomenti nell'istruzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-132">Therefore, no arguments are necessary in the calling statement.</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#6)]

2. <span data-ttu-id="fa1ff-133">Aggiungere il codice seguente alla fine del metodo per definire dove visualizzare il testo nel documento e il testo da visualizzare:</span><span class="sxs-lookup"><span data-stu-id="fa1ff-133">Add the following code at the end of the method to define where to display text in the document, and what text to display:</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#7)]

## <a name="to-run-the-application"></a><span data-ttu-id="fa1ff-134">Per eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="fa1ff-134">To run the application</span></span>

1. <span data-ttu-id="fa1ff-135">Aggiungere la seguente istruzione a Main:</span><span class="sxs-lookup"><span data-stu-id="fa1ff-135">Add the following statement to Main:</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#8)]

2. <span data-ttu-id="fa1ff-136">Premere <kbd>CTRL</kbd> + <kbd>F5</kbd> per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-136">Press <kbd>CTRL</kbd>+<kbd>F5</kbd> to run the project.</span></span> <span data-ttu-id="fa1ff-137">Verrà visualizzato un documento di Word contenente il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-137">A Word document appears that contains the specified text.</span></span>

## <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="fa1ff-138">Per convertire il testo in una tabella</span><span class="sxs-lookup"><span data-stu-id="fa1ff-138">To change the text to a table</span></span>
  
1. <span data-ttu-id="fa1ff-139">Usare il metodo `ConvertToTable` per racchiudere il testo in una tabella.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-139">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="fa1ff-140">Il metodo ha 16 parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-140">The method has sixteen optional parameters.</span></span> <span data-ttu-id="fa1ff-141">IntelliSense racchiude tra parentesi quadre i parametri facoltativi, come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-141">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>

     ![Elenco dei parametri del metodo ConvertToTable](./media/how-to-use-named-and-optional-arguments-in-office-programming/convert-table-parameters.png)

     <span data-ttu-id="fa1ff-143">Gli argomenti denominati e facoltativi consentono di specificare valori esclusivamente per i parametri che si vogliono modificare.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-143">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="fa1ff-144">Aggiungere il codice seguente alla fine del metodo `DisplayInWord` per creare una tabella semplice.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-144">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="fa1ff-145">L'argomento indica che le virgole nella stringa di testo in `range` separano le celle della tabella.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-145">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#9)]

     <span data-ttu-id="fa1ff-146">Nelle versioni precedenti di C# la chiamata a `ConvertToTable` richiede un argomento di riferimento per ogni parametro, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fa1ff-146">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code:</span></span>
  
     [!code-csharp[csProgGuideNamedAndOptional#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#14)]

2. <span data-ttu-id="fa1ff-147">Premere <kbd>CTRL</kbd> + <kbd>F5</kbd> per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-147">Press <kbd>CTRL</kbd>+<kbd>F5</kbd> to run the project.</span></span>

## <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="fa1ff-148">Per provare a usare altri parametri</span><span class="sxs-lookup"><span data-stu-id="fa1ff-148">To experiment with other parameters</span></span>

1. <span data-ttu-id="fa1ff-149">Per modificare la tabella in modo che contenga una colonna e tre righe, sostituire l'ultima riga in `DisplayInWord` con l'istruzione seguente, quindi premere <kbd>CTRL</kbd> + <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-149">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>  

     [!code-csharp[csProgGuideNamedAndOptional#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#10)]

2. <span data-ttu-id="fa1ff-150">Per specificare un formato predefinito per la tabella, sostituire l'ultima riga in `DisplayInWord` con l'istruzione seguente, quindi premere <kbd>CTRL</kbd> + <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fa1ff-150">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span> <span data-ttu-id="fa1ff-151">Il formato può corrispondere a qualsiasi costante [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>).</span><span class="sxs-lookup"><span data-stu-id="fa1ff-151">The format can be any of the [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>) constants.</span></span>

     [!code-csharp[csProgGuideNamedAndOptional#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#11)]

## <a name="example"></a><span data-ttu-id="fa1ff-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa1ff-152">Example</span></span>

<span data-ttu-id="fa1ff-153">Il codice seguente include l'esempio completo:</span><span class="sxs-lookup"><span data-stu-id="fa1ff-153">The following code includes the full example:</span></span>

 [!code-csharp[csProgGuideNamedAndOptional#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#12)]

## <a name="see-also"></a><span data-ttu-id="fa1ff-154">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fa1ff-154">See also</span></span>

- [<span data-ttu-id="fa1ff-155">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="fa1ff-155">Named and Optional Arguments</span></span>](./named-and-optional-arguments.md)
