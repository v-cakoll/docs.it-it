---
title: 'Procedura: utilizzare argomenti denominati e facoltativi nella programmazione di Office (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c773e7a6d902b9e61e724a69c9fdf5d61606de50
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="73340-102">Procedura: utilizzare argomenti denominati e facoltativi nella programmazione di Office (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="73340-102">How to: Use Named and Optional Arguments in Office Programming (C# Programming Guide)</span></span>
<span data-ttu-id="73340-103">Gli argomenti denominati e gli argomenti facoltativi, introdotti in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], migliorano la praticità, la flessibilità e la leggibilità nella programmazione C#.</span><span class="sxs-lookup"><span data-stu-id="73340-103">Named arguments and optional arguments, introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="73340-104">Queste funzionalità, poi, semplificano notevolmente l'accesso alle interfacce COM, quali le API di automazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="73340-104">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>  
  
 <span data-ttu-id="73340-105">Nell'esempio seguente, il metodo [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) dispone di sedici parametri che rappresentano le caratteristiche di una tabella, ad esempio il numero di colonne e di righe, la formattazione, i bordi, i tipi di carattere e i colori.</span><span class="sxs-lookup"><span data-stu-id="73340-105">In the following example, method [ConvertToTable](http://go.microsoft.com/fwlink/?LinkId=145378) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="73340-106">I sedici parametri sono tutti facoltativi, perché nella maggior parte dei casi non si vogliono specificare particolari valori per tutti.</span><span class="sxs-lookup"><span data-stu-id="73340-106">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="73340-107">Senza gli argomenti denominati e facoltativi, tuttavia, è necessario specificare un valore o un valore di segnaposto per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="73340-107">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="73340-108">Con gli argomenti denominati e facoltativi si specificano valori solo per i parametri obbligatori per il progetto.</span><span class="sxs-lookup"><span data-stu-id="73340-108">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>  
  
 <span data-ttu-id="73340-109">Per eseguire queste procedure, Microsoft Office Word deve essere installato.</span><span class="sxs-lookup"><span data-stu-id="73340-109">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="73340-110">Per creare un nuovo progetto di applicazione console</span><span class="sxs-lookup"><span data-stu-id="73340-110">To create a new console application</span></span>  
  
1.  <span data-ttu-id="73340-111">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="73340-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="73340-112">Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="73340-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="73340-113">Nel riquadro **Categorie di modelli** espandere **Visual C#** e quindi fare clic su **Windows**.</span><span class="sxs-lookup"><span data-stu-id="73340-113">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4.  <span data-ttu-id="73340-114">Verificare che nella parte superiore del riquadro **Modelli** sia visualizzato **.NET Framework 4** nella casella **Framework di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="73340-114">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>  
  
5.  <span data-ttu-id="73340-115">Nel riquadro **Modelli** fare clic su **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="73340-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6.  <span data-ttu-id="73340-116">Digitare un nome per il progetto nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="73340-116">Type a name for your project in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="73340-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="73340-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="73340-118">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="73340-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-a-reference"></a><span data-ttu-id="73340-119">Per aggiungere un riferimento</span><span class="sxs-lookup"><span data-stu-id="73340-119">To add a reference</span></span>  
  
1.  <span data-ttu-id="73340-120">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nome del progetto e quindi scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="73340-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="73340-121">Viene visualizzata la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="73340-121">The **Add Reference** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="73340-122">Nella pagina **.NET** selezionare **Microsoft.Office.Interop.Word** nell'elenco **Nome componente**.</span><span class="sxs-lookup"><span data-stu-id="73340-122">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>  
  
3.  <span data-ttu-id="73340-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="73340-123">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="73340-124">Per aggiungere le direttive using necessarie</span><span class="sxs-lookup"><span data-stu-id="73340-124">To add necessary using directives</span></span>  
  
1.  <span data-ttu-id="73340-125">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file **Program.cs** e quindi fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="73340-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="73340-126">Aggiungere le seguenti direttive `using` all'inizio del file di codice.</span><span class="sxs-lookup"><span data-stu-id="73340-126">Add the following `using` directives to the top of the code file.</span></span>  
  
     <span data-ttu-id="73340-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-127">[!code-cs[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]</span></span>  
  
### <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="73340-128">Per visualizzare il testo in un documento di Word</span><span class="sxs-lookup"><span data-stu-id="73340-128">To display text in a Word document</span></span>  
  
1.  <span data-ttu-id="73340-129">Nella classe `Program` in Program.cs aggiungere il metodo seguente per creare un'applicazione di Word e un documento di Word.</span><span class="sxs-lookup"><span data-stu-id="73340-129">In the `Program` class in Program.cs, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="73340-130">Il metodo [Add](http://go.microsoft.com/fwlink/?LinkId=145381) dispone di quattro parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="73340-130">The [Add](http://go.microsoft.com/fwlink/?LinkId=145381) method has four optional parameters.</span></span> <span data-ttu-id="73340-131">Questo esempio usa i relativi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="73340-131">This example uses their default values.</span></span> <span data-ttu-id="73340-132">Non sono pertanto necessari argomenti nell'istruzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="73340-132">Therefore, no arguments are necessary in the calling statement.</span></span>  
  
     <span data-ttu-id="73340-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-133">[!code-cs[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]</span></span>  
  
2.  <span data-ttu-id="73340-134">Aggiungere il codice seguente alla fine del metodo per definire il punto in cui visualizzare del testo nel documento e quale testo visualizzare.</span><span class="sxs-lookup"><span data-stu-id="73340-134">Add the following code at the end of the method to define where to display text in the document, and what text to display.</span></span>  
  
     <span data-ttu-id="73340-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-135">[!code-cs[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]</span></span>  
  
### <a name="to-run-the-application"></a><span data-ttu-id="73340-136">Per eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="73340-136">To run the application</span></span>  
  
1.  <span data-ttu-id="73340-137">Aggiungere a Main l'istruzione riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="73340-137">Add the following statement to Main.</span></span>  
  
     <span data-ttu-id="73340-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-138">[!code-cs[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]</span></span>  
  
2.  <span data-ttu-id="73340-139">Premere CTRL+F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="73340-139">Press CTRL+F5 to run the project.</span></span> <span data-ttu-id="73340-140">Verrà visualizzato un documento di Word contenente il testo specificato.</span><span class="sxs-lookup"><span data-stu-id="73340-140">A Word document appears that contains the specified text.</span></span>  
  
### <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="73340-141">Per convertire il testo in una tabella</span><span class="sxs-lookup"><span data-stu-id="73340-141">To change the text to a table</span></span>  
  
1.  <span data-ttu-id="73340-142">Usare il metodo `ConvertToTable` per racchiudere il testo in una tabella.</span><span class="sxs-lookup"><span data-stu-id="73340-142">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="73340-143">Il metodo ha 16 parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="73340-143">The method has sixteen optional parameters.</span></span> <span data-ttu-id="73340-144">IntelliSense racchiude tra parentesi quadre i parametri facoltativi, come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="73340-144">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="73340-145">![Elenco dei parametri del metodo ConvertToTable.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span><span class="sxs-lookup"><span data-stu-id="73340-145">![List of parameters for ConvertToTable method.](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")</span></span>  
<span data-ttu-id="73340-146">Parametri di ConvertToTable</span><span class="sxs-lookup"><span data-stu-id="73340-146">ConvertToTable parameters</span></span>  
  
     <span data-ttu-id="73340-147">Gli argomenti denominati e facoltativi consentono di specificare valori esclusivamente per i parametri che si vogliono modificare.</span><span class="sxs-lookup"><span data-stu-id="73340-147">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="73340-148">Aggiungere il codice seguente alla fine del metodo `DisplayInWord` per creare una tabella semplice.</span><span class="sxs-lookup"><span data-stu-id="73340-148">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="73340-149">L'argomento indica che le virgole nella stringa di testo in `range` separano le celle della tabella.</span><span class="sxs-lookup"><span data-stu-id="73340-149">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>  
  
     <span data-ttu-id="73340-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-150">[!code-cs[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]</span></span>  
  
     <span data-ttu-id="73340-151">Nelle versioni precedenti di C# la chiamata a `ConvertToTable` richiede un argomento di riferimento per ogni parametro, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="73340-151">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code.</span></span>  
  
     <span data-ttu-id="73340-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-152">[!code-cs[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]</span></span>  
  
2.  <span data-ttu-id="73340-153">Premere CTRL+F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="73340-153">Press CTRL+F5 to run the project.</span></span>  
  
### <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="73340-154">Per provare a usare altri parametri</span><span class="sxs-lookup"><span data-stu-id="73340-154">To experiment with other parameters</span></span>  
  
1.  <span data-ttu-id="73340-155">Per modificare la tabella in modo che contenga una colonna e tre righe, sostituire l'ultima riga in `DisplayInWord` con l'istruzione seguente, quindi premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="73340-155">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span>  
  
     <span data-ttu-id="73340-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-156">[!code-cs[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]</span></span>  
  
2.  <span data-ttu-id="73340-157">Per specificare un formato predefinito per la tabella, sostituire l'ultima riga in `DisplayInWord` con l'istruzione seguente, quindi premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="73340-157">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span> <span data-ttu-id="73340-158">Il formato può corrispondere a qualsiasi costante [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382).</span><span class="sxs-lookup"><span data-stu-id="73340-158">The format can be any of the [WdTableFormat](http://go.microsoft.com/fwlink/?LinkId=145382) constants.</span></span>  
  
     <span data-ttu-id="73340-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-159">[!code-cs[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="73340-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="73340-160">Example</span></span>  
 <span data-ttu-id="73340-161">Il codice seguente include l'esempio completo.</span><span class="sxs-lookup"><span data-stu-id="73340-161">The following code includes the full example.</span></span>  
  
 <span data-ttu-id="73340-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="73340-162">[!code-cs[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73340-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73340-163">See Also</span></span>  
 [<span data-ttu-id="73340-164">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="73340-164">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)

