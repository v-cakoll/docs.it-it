---
title: Commenti nel codice (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: fafc80cc4847e9ec05f19fc7f3d31d2d5b11197a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43870341"
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="af81d-102">Commenti nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af81d-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="af81d-103">Negli esempi di codice viene spesso utilizzato il simbolo di commento (`'`).</span><span class="sxs-lookup"><span data-stu-id="af81d-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="af81d-104">Questo simbolo indica al compilatore di Visual Basic per ignorare il testo seguente, o la *commento*.</span><span class="sxs-lookup"><span data-stu-id="af81d-104">This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="af81d-105">I commenti sono brevi annotazioni descrittive che vengono aggiunte al codice per agevolarne la lettura.</span><span class="sxs-lookup"><span data-stu-id="af81d-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="af81d-106">È buona norma di programmazione iniziare tutte le routine con un breve commento che ne descriva le caratteristiche funzionali, ovvero le operazioni che vengono compiute.</span><span class="sxs-lookup"><span data-stu-id="af81d-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="af81d-107">Ciò può rivelarsi a proprio vantaggio e di chi esaminerà il codice.</span><span class="sxs-lookup"><span data-stu-id="af81d-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="af81d-108">È opportuno separare le informazioni dettagliate relative alle modalità di implementazione dai commenti che descrivono le caratteristiche funzionali.</span><span class="sxs-lookup"><span data-stu-id="af81d-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="af81d-109">Quando si includono informazioni dettagliate sulle modalità di implementazione, è importante che queste vengano aggiornate contestualmente all'aggiornamento della funzione.</span><span class="sxs-lookup"><span data-stu-id="af81d-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="af81d-110">I commenti possono seguire un'istruzione sulla stessa riga oppure occupare una riga intera.</span><span class="sxs-lookup"><span data-stu-id="af81d-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="af81d-111">Nell'esempio di codice seguente vengono illustrate entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="af81d-111">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 <span data-ttu-id="af81d-112">Se il commento richiede più di una riga, utilizzare il simbolo di commento su ogni riga, così come viene illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="af81d-112">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="af81d-113">Indicazioni sui commenti</span><span class="sxs-lookup"><span data-stu-id="af81d-113">Commenting Guidelines</span></span>  
 <span data-ttu-id="af81d-114">Nella tabella riportata di seguito vengono fornite indicazioni generali sui tipi di commenti che possono precedere una sezione del codice.</span><span class="sxs-lookup"><span data-stu-id="af81d-114">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="af81d-115">Questi sono i suggerimenti; Visual Basic non applica le regole per l'aggiunta di commenti.</span><span class="sxs-lookup"><span data-stu-id="af81d-115">These are suggestions; Visual Basic does not enforce rules for adding comments.</span></span> <span data-ttu-id="af81d-116">Scrivere il testo che si ritiene più adatto alle proprie esigenze e a quelle di chi leggerà il codice.</span><span class="sxs-lookup"><span data-stu-id="af81d-116">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="af81d-117">Tipo di commento</span><span class="sxs-lookup"><span data-stu-id="af81d-117">Comment type</span></span>|<span data-ttu-id="af81d-118">Descrizione del commento</span><span class="sxs-lookup"><span data-stu-id="af81d-118">Comment description</span></span>|  
|<span data-ttu-id="af81d-119">Scopo</span><span class="sxs-lookup"><span data-stu-id="af81d-119">Purpose</span></span>|<span data-ttu-id="af81d-120">Descrive le operazioni eseguite dalla routine, non la modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="af81d-120">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="af81d-121">Presupposti</span><span class="sxs-lookup"><span data-stu-id="af81d-121">Assumptions</span></span>|<span data-ttu-id="af81d-122">Elenca tutte le variabili esterne, i controlli, i file aperti o gli altri elementi a cui accede la routine</span><span class="sxs-lookup"><span data-stu-id="af81d-122">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="af81d-123">Effetti</span><span class="sxs-lookup"><span data-stu-id="af81d-123">Effects</span></span>|<span data-ttu-id="af81d-124">Elenca tutte le variabili esterne, i controlli o i file interessati, nonché l'effetto su di essi (solo se non è ovvio)</span><span class="sxs-lookup"><span data-stu-id="af81d-124">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="af81d-125">Input</span><span class="sxs-lookup"><span data-stu-id="af81d-125">Inputs</span></span>|<span data-ttu-id="af81d-126">Specifica lo scopo dell'argomento</span><span class="sxs-lookup"><span data-stu-id="af81d-126">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="af81d-127">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af81d-127">Returns</span></span>|<span data-ttu-id="af81d-128">Spiega i valori restituiti dalla routine</span><span class="sxs-lookup"><span data-stu-id="af81d-128">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="af81d-129">È importante tenere presente i seguenti punti:</span><span class="sxs-lookup"><span data-stu-id="af81d-129">Remember the following points:</span></span>  
  
-   <span data-ttu-id="af81d-130">Le dichiarazioni di variabili importanti devono essere precedute da un commento in cui viene descritto l'utilizzo della variabile dichiarata.</span><span class="sxs-lookup"><span data-stu-id="af81d-130">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
-   <span data-ttu-id="af81d-131">I nomi di variabili, controlli e routine devono essere descrittivi in modo da rendere necessaria l'aggiunta di commenti solo per la descrizione di implementazioni complesse.</span><span class="sxs-lookup"><span data-stu-id="af81d-131">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
-   <span data-ttu-id="af81d-132">Non è possibile inserire sulla stessa riga una sequenza di continuazione di riga seguita da un commento.</span><span class="sxs-lookup"><span data-stu-id="af81d-132">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="af81d-133">È possibile aggiungere o rimuovere i simboli di commento per un blocco di codice, selezionare uno o più righe di codice e scegliere il **commento** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton ")) e **Rimuovi commento** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) i pulsanti sul **modifica**  sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="af81d-133">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) and **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af81d-134">Per aggiungere commenti al codice è possibile anche inserire la parola chiave `REM` prima del testo.</span><span class="sxs-lookup"><span data-stu-id="af81d-134">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="af81d-135">Tuttavia, il `'` simbolo e il **commento**/**Rimuovi commento** pulsanti sono più facili da usare e richiedono meno spazio e memoria.</span><span class="sxs-lookup"><span data-stu-id="af81d-135">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af81d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af81d-136">See Also</span></span>  
 [<span data-ttu-id="af81d-137">Documentazione del codice con commenti XML</span><span class="sxs-lookup"><span data-stu-id="af81d-137">Documenting Your Code With XML Comments</span></span>](https://msdn.microsoft.com/magazine/dd722812.aspx)  
 [<span data-ttu-id="af81d-138">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="af81d-138">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="af81d-139">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="af81d-139">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)  
 [<span data-ttu-id="af81d-140">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="af81d-140">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="af81d-141">Istruzione REM</span><span class="sxs-lookup"><span data-stu-id="af81d-141">REM Statement</span></span>](../../../visual-basic/language-reference/statements/rem-statement.md)
