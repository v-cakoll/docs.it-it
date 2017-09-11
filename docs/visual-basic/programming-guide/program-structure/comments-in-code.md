---
title: I commenti nel codice (Visual Basic) | Documenti di Microsoft
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
- Uncomment button
- REM statement
- comments, in code
- comments, Visual Basic code
- Comment button
- buttons, Uncomment
- buttons, Comment
- code comments, Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: 17
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
ms.openlocfilehash: e872c9bb67835573aadcc1016f2c6a98d434201e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="732b2-102">Commenti nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="732b2-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="732b2-103">Negli esempi di codice viene spesso utilizzato il simbolo di commento (`'`).</span><span class="sxs-lookup"><span data-stu-id="732b2-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="732b2-104">Questo simbolo indica il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore di ignorare il testo seguente, o *commento*.</span><span class="sxs-lookup"><span data-stu-id="732b2-104">This symbol tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="732b2-105">I commenti sono brevi annotazioni descrittive che vengono aggiunte al codice per agevolarne la lettura.</span><span class="sxs-lookup"><span data-stu-id="732b2-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="732b2-106">È buona norma di programmazione iniziare tutte le routine con un breve commento che ne descriva le caratteristiche funzionali, ovvero le operazioni che vengono compiute.</span><span class="sxs-lookup"><span data-stu-id="732b2-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="732b2-107">Ciò può rivelarsi a proprio vantaggio e di chi esaminerà il codice.</span><span class="sxs-lookup"><span data-stu-id="732b2-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="732b2-108">È opportuno separare le informazioni dettagliate relative alle modalità di implementazione dai commenti che descrivono le caratteristiche funzionali.</span><span class="sxs-lookup"><span data-stu-id="732b2-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="732b2-109">Quando si includono informazioni dettagliate sulle modalità di implementazione, è importante che queste vengano aggiornate contestualmente all'aggiornamento della funzione.</span><span class="sxs-lookup"><span data-stu-id="732b2-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="732b2-110">I commenti possono seguire un'istruzione sulla stessa riga oppure occupare una riga intera.</span><span class="sxs-lookup"><span data-stu-id="732b2-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="732b2-111">Nell'esempio di codice seguente vengono illustrate entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="732b2-111">Both are illustrated in the following code.</span></span>  
  
 <span data-ttu-id="732b2-112">[!code-vb[VbVbcnConventions&#16;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="732b2-112">[!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="732b2-113">Se il commento richiede più di una riga, utilizzare il simbolo di commento su ogni riga, così come viene illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="732b2-113">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 <span data-ttu-id="732b2-114">[!code-vb[VbVbcnConventions n.&17;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="732b2-114">[!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]</span></span>  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="732b2-115">Indicazioni sui commenti</span><span class="sxs-lookup"><span data-stu-id="732b2-115">Commenting Guidelines</span></span>  
 <span data-ttu-id="732b2-116">Nella tabella riportata di seguito vengono fornite indicazioni generali sui tipi di commenti che possono precedere una sezione del codice.</span><span class="sxs-lookup"><span data-stu-id="732b2-116">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="732b2-117">Si tratta di semplici suggerimenti; [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non impone alcuna regola per l'aggiunta di commenti.</span><span class="sxs-lookup"><span data-stu-id="732b2-117">These are suggestions; [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not enforce rules for adding comments.</span></span> <span data-ttu-id="732b2-118">Scrivere il testo che si ritiene più adatto alle proprie esigenze e a quelle di chi leggerà il codice.</span><span class="sxs-lookup"><span data-stu-id="732b2-118">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="732b2-119">Tipo di commento</span><span class="sxs-lookup"><span data-stu-id="732b2-119">Comment type</span></span>|<span data-ttu-id="732b2-120">Descrizione del commento</span><span class="sxs-lookup"><span data-stu-id="732b2-120">Comment description</span></span>|  
|<span data-ttu-id="732b2-121">Scopo</span><span class="sxs-lookup"><span data-stu-id="732b2-121">Purpose</span></span>|<span data-ttu-id="732b2-122">Descrive le operazioni eseguite dalla routine, non la modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="732b2-122">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="732b2-123">Presupposti</span><span class="sxs-lookup"><span data-stu-id="732b2-123">Assumptions</span></span>|<span data-ttu-id="732b2-124">Elenca tutte le variabili esterne, i controlli, i file aperti o gli altri elementi a cui accede la routine</span><span class="sxs-lookup"><span data-stu-id="732b2-124">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="732b2-125">Effetti</span><span class="sxs-lookup"><span data-stu-id="732b2-125">Effects</span></span>|<span data-ttu-id="732b2-126">Elenca tutte le variabili esterne, i controlli o i file interessati, nonché l'effetto su di essi (solo se non è ovvio)</span><span class="sxs-lookup"><span data-stu-id="732b2-126">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="732b2-127">Input</span><span class="sxs-lookup"><span data-stu-id="732b2-127">Inputs</span></span>|<span data-ttu-id="732b2-128">Specifica lo scopo dell'argomento</span><span class="sxs-lookup"><span data-stu-id="732b2-128">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="732b2-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="732b2-129">Returns</span></span>|<span data-ttu-id="732b2-130">Spiega i valori restituiti dalla routine</span><span class="sxs-lookup"><span data-stu-id="732b2-130">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="732b2-131">È importante tenere presente i seguenti punti:</span><span class="sxs-lookup"><span data-stu-id="732b2-131">Remember the following points:</span></span>  
  
-   <span data-ttu-id="732b2-132">Le dichiarazioni di variabili importanti devono essere precedute da un commento in cui viene descritto l'utilizzo della variabile dichiarata.</span><span class="sxs-lookup"><span data-stu-id="732b2-132">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
-   <span data-ttu-id="732b2-133">I nomi di variabili, controlli e routine devono essere descrittivi in modo da rendere necessaria l'aggiunta di commenti solo per la descrizione di implementazioni complesse.</span><span class="sxs-lookup"><span data-stu-id="732b2-133">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
-   <span data-ttu-id="732b2-134">Non è possibile inserire sulla stessa riga una sequenza di continuazione di riga seguita da un commento.</span><span class="sxs-lookup"><span data-stu-id="732b2-134">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="732b2-135">È possibile aggiungere o rimuovere i simboli di commento per un blocco di codice, selezionare uno o più righe di codice e scegliere il **commento** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) e **Rimuovi commento** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) pulsanti di **modificare** barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="732b2-135">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) and **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="732b2-136">Per aggiungere commenti al codice è possibile anche inserire la parola chiave `REM` prima del testo.</span><span class="sxs-lookup"><span data-stu-id="732b2-136">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="732b2-137">Tuttavia, il `'` simbolo e il **commento**/**Rimuovi commento** pulsanti sono più facili da utilizzare e richiedono meno spazio e memoria.</span><span class="sxs-lookup"><span data-stu-id="732b2-137">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732b2-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="732b2-138">See Also</span></span>  
 <span data-ttu-id="732b2-139">[La documentazione del codice con commenti XML](http://msdn.microsoft.com/magazine/dd722812.aspx) </span><span class="sxs-lookup"><span data-stu-id="732b2-139">[Documenting Your Code With XML Comments](http://msdn.microsoft.com/magazine/dd722812.aspx) </span></span>  
<span data-ttu-id="732b2-140"> [Procedura: creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="732b2-140"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md) </span></span>  
<span data-ttu-id="732b2-141"> [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="732b2-141"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="732b2-142"> [Struttura del programma e convenzioni del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="732b2-142"> [Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="732b2-143"> [Istruzione REM](../../../visual-basic/language-reference/statements/rem-statement.md)</span><span class="sxs-lookup"><span data-stu-id="732b2-143"> [REM Statement](../../../visual-basic/language-reference/statements/rem-statement.md)</span></span>
