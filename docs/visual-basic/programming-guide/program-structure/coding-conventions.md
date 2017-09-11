---
title: Convenzioni di codifica di Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- coding conventions, Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 16d4ddccd3a16c48e58f297faf8909148899013f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="c097c-102">Convenzioni di codifica di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c097c-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="c097c-103">Microsoft sviluppa esempi e documentazione che seguire le istruzioni in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c097c-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="c097c-104">Se si seguono le stesse convenzioni di codifica, è possibile ottenere i seguenti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="c097c-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="c097c-105">Il codice avrà un aspetto coerente, in modo che chi legge possa concentrarsi meglio sul contenuto, non layout.</span><span class="sxs-lookup"><span data-stu-id="c097c-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="c097c-106">Lettori di comprendere il codice più rapidamente poiché è possibile apportare presupposti basati sulle esperienze precedenti.</span><span class="sxs-lookup"><span data-stu-id="c097c-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="c097c-107">È possibile copiare, modificare e gestire più facilmente il codice.</span><span class="sxs-lookup"><span data-stu-id="c097c-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="c097c-108">Consente di assicurare che il codice viene illustrato "procedure consigliate" per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c097c-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="c097c-109">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c097c-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="c097c-110">Per informazioni sulle linee guida per la denominazione, vedere [convenzioni di denominazione per](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) argomento.</span><span class="sxs-lookup"><span data-stu-id="c097c-110">For information about naming guidelines, see [Naming Guidelines](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) topic.</span></span>  
  
-   <span data-ttu-id="c097c-111">Non utilizzare "My" o "my" come parte di un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="c097c-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="c097c-112">Questa procedura crea confusione con il `My` oggetti.</span><span class="sxs-lookup"><span data-stu-id="c097c-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="c097c-113">Non è necessario modificare i nomi degli oggetti nel codice generato automaticamente per adattare le linee guida.</span><span class="sxs-lookup"><span data-stu-id="c097c-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="c097c-114">Convenzioni di layout</span><span class="sxs-lookup"><span data-stu-id="c097c-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="c097c-115">Inserire le schede come spazi e utilizzare rientri intelligenti con rientri di quattro spazi.</span><span class="sxs-lookup"><span data-stu-id="c097c-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="c097c-116">Utilizzare **riformattazione del listato di codice (riformattazione) di** di riformattare il codice nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="c097c-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="c097c-117">Per ulteriori informazioni, vedere [opzioni, Editor di testo, base (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c097c-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="c097c-118">Utilizzare solo un'istruzione per riga.</span><span class="sxs-lookup"><span data-stu-id="c097c-118">Use only one statement per line.</span></span> <span data-ttu-id="c097c-119">Non utilizzare il carattere di separatore di riga (:) di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c097c-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="c097c-120">Evitare di utilizzare il carattere di continuazione di riga esplicita "_" a favore di continuazione di riga implicita ovunque il linguaggio consente.</span><span class="sxs-lookup"><span data-stu-id="c097c-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="c097c-121">Utilizzare una sola dichiarazione per riga.</span><span class="sxs-lookup"><span data-stu-id="c097c-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="c097c-122">Se **riformattazione del listato di codice (riformattazione) di** non righe di continuazione formato automaticamente, manualmente rientro continuazione righe di una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="c097c-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="c097c-123">Tuttavia, sempre sinistra-Allinea elementi in un elenco.</span><span class="sxs-lookup"><span data-stu-id="c097c-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="c097c-124">Aggiungere almeno una riga vuota tra le definizioni di metodo e proprietà.</span><span class="sxs-lookup"><span data-stu-id="c097c-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="c097c-125">Convenzioni relative ai commenti</span><span class="sxs-lookup"><span data-stu-id="c097c-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="c097c-126">Inserire i commenti su una riga separata anziché alla fine di una riga di codice.</span><span class="sxs-lookup"><span data-stu-id="c097c-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="c097c-127">Avviare commento con una lettera maiuscola e fine commento con un punto.</span><span class="sxs-lookup"><span data-stu-id="c097c-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="c097c-128">Inserire uno spazio tra i delimitatori di commento (') e il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="c097c-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     <span data-ttu-id="c097c-129">[!code-vb[VbVbalrGuidelines n.&2;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-129">[!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-130">Non racchiudere i commenti con blocchi formattati di asterischi.</span><span class="sxs-lookup"><span data-stu-id="c097c-130">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="c097c-131">Struttura del programma</span><span class="sxs-lookup"><span data-stu-id="c097c-131">Program Structure</span></span>  
  
-   <span data-ttu-id="c097c-132">Quando si utilizza il `Main` (metodo), utilizzare il costrutto predefinito per le nuove applicazioni console e `My` per gli argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c097c-132">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     <span data-ttu-id="c097c-133">[!code-vb[VbVbalrGuidelines n.&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-133">[!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="c097c-134">Linee guida della lingua</span><span class="sxs-lookup"><span data-stu-id="c097c-134">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="c097c-135">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="c097c-135">String Data Type</span></span>  
  
-   <span data-ttu-id="c097c-136">Per concatenare stringhe, utilizzare una e commerciale (&).</span><span class="sxs-lookup"><span data-stu-id="c097c-136">To concatenate strings, use an ampersand (&).</span></span>  
  
     <span data-ttu-id="c097c-137">[!code-vb[VbVbalrGuidelines n.&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-137">[!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-138">Per accodare stringhe nei cicli, utilizzare il <xref:System.Text.StringBuilder>oggetto.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="c097c-138">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="c097c-139">[!code-vb[VbVbalrGuidelines n.&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-139">[!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span></span>  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="c097c-140">Delegati di tipo relaxed nei gestori eventi</span><span class="sxs-lookup"><span data-stu-id="c097c-140">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="c097c-141">Non qualificare in modo esplicito gli argomenti (oggetto ed EventArgs) ai gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="c097c-141">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="c097c-142">Se non si utilizza gli argomenti dell'evento che vengono passati a un evento (ad esempio mittente come oggetto, e come EventArgs), utilizzare i delegati di tipo relaxed e omettere gli argomenti dell'evento nel codice:</span><span class="sxs-lookup"><span data-stu-id="c097c-142">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 <span data-ttu-id="c097c-143">[!code-vb[VbVbalrGuidelines&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-143">[!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="c097c-144">Tipi di dati non firmati</span><span class="sxs-lookup"><span data-stu-id="c097c-144">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="c097c-145">Utilizzare `Integer` anziché tipi non firmati, tranne quando sono necessari.</span><span class="sxs-lookup"><span data-stu-id="c097c-145">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="c097c-146">Matrici</span><span class="sxs-lookup"><span data-stu-id="c097c-146">Arrays</span></span>  
  
-   <span data-ttu-id="c097c-147">Utilizzare la sintassi breve quando si inizializzano le matrici nella riga della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c097c-147">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="c097c-148">Ad esempio, utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="c097c-148">For example, use the following syntax.</span></span>  
  
     <span data-ttu-id="c097c-149">[!code-vb[VbVbalrGuidelines n.&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-149">[!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span></span>  
  
     <span data-ttu-id="c097c-150">Non utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="c097c-150">Do not use the following syntax.</span></span>  
  
     <span data-ttu-id="c097c-151">[!code-vb[9 VbVbalrGuidelines](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-151">[!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-152">Inserire l'identificatore di matrice del tipo, non sulla variabile.</span><span class="sxs-lookup"><span data-stu-id="c097c-152">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="c097c-153">Ad esempio, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c097c-153">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="c097c-154">[!code-vb[VbVbalrGuidelines&#11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-154">[!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span></span>  
  
     <span data-ttu-id="c097c-155">Non utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c097c-155">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="c097c-156">[!code-vb[VbVbalrGuidelines&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-156">[!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-157">Utilizzare la sintassi {} quando è necessario dichiarare e inizializzare matrici di tipi di dati di base.</span><span class="sxs-lookup"><span data-stu-id="c097c-157">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="c097c-158">Ad esempio, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c097c-158">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="c097c-159">[!code-vb[VbVbalrGuidelines&#12;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-159">[!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span></span>  
  
     <span data-ttu-id="c097c-160">Non utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c097c-160">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="c097c-161">[!code-vb[13 VbVbalrGuidelines](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-161">[!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span></span>  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="c097c-162">Utilizzare la parola chiave</span><span class="sxs-lookup"><span data-stu-id="c097c-162">Use the With Keyword</span></span>  
 <span data-ttu-id="c097c-163">Quando si esegue una serie di chiamate a un oggetto, è consigliabile utilizzare il `With` (parola chiave):</span><span class="sxs-lookup"><span data-stu-id="c097c-163">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 <span data-ttu-id="c097c-164">[!code-vb[VbVbalrGuidelines&#15;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-164">[!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span></span>  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="c097c-165">Utilizzare l'istruzione Try... Catch e utilizzo di istruzioni quando si utilizza la gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c097c-165">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="c097c-166">Non utilizzare `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="c097c-166">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="c097c-167">Utilizzare la parola chiave IsNot</span><span class="sxs-lookup"><span data-stu-id="c097c-167">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="c097c-168">Utilizzare il `IsNot` (parola chiave) anziché `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="c097c-168">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="c097c-169">Parola chiave New</span><span class="sxs-lookup"><span data-stu-id="c097c-169">New Keyword</span></span>  
  
-   <span data-ttu-id="c097c-170">Utilizzare l'istanziazione breve.</span><span class="sxs-lookup"><span data-stu-id="c097c-170">Use short instantiation.</span></span> <span data-ttu-id="c097c-171">Ad esempio, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c097c-171">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="c097c-172">[!code-vb[VbVbalrGuidelines numero&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-172">[!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span></span>  
  
     <span data-ttu-id="c097c-173">La riga precedente è equivalente a questa:</span><span class="sxs-lookup"><span data-stu-id="c097c-173">The preceding line is equivalent to this:</span></span>  
  
     <span data-ttu-id="c097c-174">[!code-vb[VbVbalrGuidelines&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-174">[!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-175">Utilizzare gli inizializzatori di oggetto per i nuovi oggetti anziché il costruttore senza parametri:</span><span class="sxs-lookup"><span data-stu-id="c097c-175">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     <span data-ttu-id="c097c-176">[!code-vb[VbVbalrGuidelines&#23;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-176">[!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="c097c-177">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="c097c-177">Event Handling</span></span>  
  
-   <span data-ttu-id="c097c-178">Utilizzare `Handles` anziché `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="c097c-178">Use `Handles` rather than `AddHandler`:</span></span>  
  
     <span data-ttu-id="c097c-179">[!code-vb[VbVbalrGuidelines&#24;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-179">[!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-180">Utilizzare `AddressOf`e non creare un'istanza del delegato in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="c097c-180">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     <span data-ttu-id="c097c-181">[!code-vb[VbVbalrGuidelines&#25;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-181">[!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-182">Quando si definisce un evento, utilizzare la sintassi breve e consentire al compilatore di definire il delegato:</span><span class="sxs-lookup"><span data-stu-id="c097c-182">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     <span data-ttu-id="c097c-183">[!code-vb[&#26; VbVbalrGuidelines](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-183">[!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-184">Verifica se un evento è `Nothing` (null) prima di chiamare il `RaiseEvent` metodo.</span><span class="sxs-lookup"><span data-stu-id="c097c-184">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="c097c-185">`RaiseEvent`Cerca `Nothing` prima che venga generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="c097c-185">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="c097c-186">Utilizzo di membri condivisi</span><span class="sxs-lookup"><span data-stu-id="c097c-186">Using Shared Members</span></span>  
 <span data-ttu-id="c097c-187">Chiamare `Shared` membri utilizzando il nome della classe, non una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="c097c-187">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="c097c-188">Utilizzare valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="c097c-188">Use XML Literals</span></span>  
 <span data-ttu-id="c097c-189">Valori letterali XML semplificano le attività più comuni che si verificano quando si lavora con XML (ad esempio, query, trasformazione e caricamento).</span><span class="sxs-lookup"><span data-stu-id="c097c-189">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="c097c-190">Quando si sviluppa con XML, attenersi alle seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="c097c-190">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="c097c-191">Utilizzare valori letterali XML per creare documenti e frammenti anziché chiamare direttamente le API XML XML.</span><span class="sxs-lookup"><span data-stu-id="c097c-191">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="c097c-192">Importare gli spazi dei nomi XML a livello di file o progetto in modo da sfruttare le ottimizzazioni delle prestazioni per i valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="c097c-192">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="c097c-193">Utilizzare le proprietà axis XML per accedere agli elementi e attributi in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="c097c-193">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="c097c-194">Utilizzare le espressioni incorporate per includere i valori e creare XML da valori esistenti anziché utilizzare chiamate API, ad esempio il `Add` metodo:</span><span class="sxs-lookup"><span data-stu-id="c097c-194">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     <span data-ttu-id="c097c-195">[!code-vb[VbVbalrGuidelines&#27;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-195">[!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="c097c-196">Query LINQ</span><span class="sxs-lookup"><span data-stu-id="c097c-196">LINQ Queries</span></span>  
  
-   <span data-ttu-id="c097c-197">Utilizzare nomi significativi per le variabili di query:</span><span class="sxs-lookup"><span data-stu-id="c097c-197">Use meaningful names for query variables:</span></span>  
  
     <span data-ttu-id="c097c-198">[!code-vb[28 VbVbalrGuidelines](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-198">[!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-199">Fornire nomi di elementi in una query per assicurarsi che i nomi di proprietà di tipi anonimi sono in modo corretto utilizzando la convenzione Pascal maiuscole e minuscole:</span><span class="sxs-lookup"><span data-stu-id="c097c-199">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     <span data-ttu-id="c097c-200">[!code-vb[VbVbalrGuidelines&#29;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-200">[!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-201">Rinominare le proprietà quando i nomi delle proprietà nel risultato potrebbero risultare ambigui.</span><span class="sxs-lookup"><span data-stu-id="c097c-201">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="c097c-202">Ad esempio, se la query restituisce un nome cliente un ID ordine, rinominarle anziché lasciarli come `Name` e `ID` nel risultato:</span><span class="sxs-lookup"><span data-stu-id="c097c-202">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     <span data-ttu-id="c097c-203">[!code-vb[&#30; VbVbalrGuidelines](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-203">[!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-204">Utilizzare l'inferenza del tipo nella dichiarazione di variabili di query e variabili di intervallo:</span><span class="sxs-lookup"><span data-stu-id="c097c-204">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     <span data-ttu-id="c097c-205">[!code-vb[VbVbalrGuidelines&#31;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-205">[!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-206">Allineare le clausole di query sotto il `From` istruzione:</span><span class="sxs-lookup"><span data-stu-id="c097c-206">Align query clauses under the `From` statement:</span></span>  
  
     <span data-ttu-id="c097c-207">[!code-vb[VbVbalrGuidelines n.&32;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-207">[!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-208">Utilizzare `Where` clausole prima delle altre clausole di query in modo che successive clausole di query agiscano su set di dati filtrati:</span><span class="sxs-lookup"><span data-stu-id="c097c-208">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     <span data-ttu-id="c097c-209">[!code-vb[VbVbalrGuidelines n.&33;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-209">[!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span></span>  
  
-   <span data-ttu-id="c097c-210">Utilizzare il `Join` clausola per definire in modo esplicito un'operazione di join anziché il `Where` clausola per definire in modo implicito un'operazione di join:</span><span class="sxs-lookup"><span data-stu-id="c097c-210">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     <span data-ttu-id="c097c-211">[!code-vb[VbVbalrGuidelines&#34;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span><span class="sxs-lookup"><span data-stu-id="c097c-211">[!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c097c-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c097c-212">See Also</span></span>  
 [<span data-ttu-id="c097c-213">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="c097c-213">Secure Coding Guidelines</span></span>](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
