---
title: Commenti nel codice
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
ms.openlocfilehash: b50e76b8f832c3a214ca54f97bab8b0b6789ac25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403317"
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="bce50-102">Commenti nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce50-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="bce50-103">Negli esempi di codice viene spesso utilizzato il simbolo di commento (`'`).</span><span class="sxs-lookup"><span data-stu-id="bce50-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="bce50-104">Questo simbolo indica al compilatore Visual Basic di ignorare il testo che lo segue o il *Commento*.</span><span class="sxs-lookup"><span data-stu-id="bce50-104">This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="bce50-105">I commenti sono brevi annotazioni descrittive che vengono aggiunte al codice per agevolarne la lettura.</span><span class="sxs-lookup"><span data-stu-id="bce50-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="bce50-106">È buona norma di programmazione iniziare tutte le routine con un breve commento che ne descriva le caratteristiche funzionali, ovvero le operazioni che vengono compiute.</span><span class="sxs-lookup"><span data-stu-id="bce50-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="bce50-107">Ciò può rivelarsi a proprio vantaggio e di chi esaminerà il codice.</span><span class="sxs-lookup"><span data-stu-id="bce50-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="bce50-108">È opportuno separare le informazioni dettagliate relative alle modalità di implementazione dai commenti che descrivono le caratteristiche funzionali.</span><span class="sxs-lookup"><span data-stu-id="bce50-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="bce50-109">Quando si includono informazioni dettagliate sulle modalità di implementazione, è importante che queste vengano aggiornate contestualmente all'aggiornamento della funzione.</span><span class="sxs-lookup"><span data-stu-id="bce50-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="bce50-110">I commenti possono seguire un'istruzione sulla stessa riga oppure occupare una riga intera.</span><span class="sxs-lookup"><span data-stu-id="bce50-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="bce50-111">Nell'esempio di codice seguente vengono illustrate entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="bce50-111">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 <span data-ttu-id="bce50-112">Se il commento richiede più di una riga, utilizzare il simbolo di commento su ogni riga, così come viene illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bce50-112">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="bce50-113">Indicazioni sui commenti</span><span class="sxs-lookup"><span data-stu-id="bce50-113">Commenting Guidelines</span></span>  
 <span data-ttu-id="bce50-114">Nella tabella riportata di seguito vengono fornite indicazioni generali sui tipi di commenti che possono precedere una sezione del codice.</span><span class="sxs-lookup"><span data-stu-id="bce50-114">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="bce50-115">Si tratta di suggerimenti; Visual Basic non impone regole per l'aggiunta di commenti.</span><span class="sxs-lookup"><span data-stu-id="bce50-115">These are suggestions; Visual Basic does not enforce rules for adding comments.</span></span> <span data-ttu-id="bce50-116">Scrivere il testo che si ritiene più adatto alle proprie esigenze e a quelle di chi leggerà il codice.</span><span class="sxs-lookup"><span data-stu-id="bce50-116">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="bce50-117">Tipo di commento</span><span class="sxs-lookup"><span data-stu-id="bce50-117">Comment type</span></span>|<span data-ttu-id="bce50-118">Descrizione del commento</span><span class="sxs-lookup"><span data-stu-id="bce50-118">Comment description</span></span>|  
|<span data-ttu-id="bce50-119">Scopo</span><span class="sxs-lookup"><span data-stu-id="bce50-119">Purpose</span></span>|<span data-ttu-id="bce50-120">Descrive le operazioni eseguite dalla routine, non la modalità di esecuzione</span><span class="sxs-lookup"><span data-stu-id="bce50-120">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="bce50-121">Presupposti</span><span class="sxs-lookup"><span data-stu-id="bce50-121">Assumptions</span></span>|<span data-ttu-id="bce50-122">Elenca tutte le variabili esterne, i controlli, i file aperti o gli altri elementi a cui accede la routine</span><span class="sxs-lookup"><span data-stu-id="bce50-122">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="bce50-123">Effetti</span><span class="sxs-lookup"><span data-stu-id="bce50-123">Effects</span></span>|<span data-ttu-id="bce50-124">Elenca tutte le variabili esterne, i controlli o i file interessati, nonché l'effetto su di essi (solo se non è ovvio)</span><span class="sxs-lookup"><span data-stu-id="bce50-124">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="bce50-125">Input</span><span class="sxs-lookup"><span data-stu-id="bce50-125">Inputs</span></span>|<span data-ttu-id="bce50-126">Specifica lo scopo dell'argomento</span><span class="sxs-lookup"><span data-stu-id="bce50-126">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="bce50-127">Valori di codice restituiti</span><span class="sxs-lookup"><span data-stu-id="bce50-127">Returns</span></span>|<span data-ttu-id="bce50-128">Spiega i valori restituiti dalla routine</span><span class="sxs-lookup"><span data-stu-id="bce50-128">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="bce50-129">È importante tenere presente i seguenti punti:</span><span class="sxs-lookup"><span data-stu-id="bce50-129">Remember the following points:</span></span>  
  
- <span data-ttu-id="bce50-130">Le dichiarazioni di variabili importanti devono essere precedute da un commento in cui viene descritto l'utilizzo della variabile dichiarata.</span><span class="sxs-lookup"><span data-stu-id="bce50-130">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
- <span data-ttu-id="bce50-131">I nomi di variabili, controlli e routine devono essere descrittivi in modo da rendere necessaria l'aggiunta di commenti solo per la descrizione di implementazioni complesse.</span><span class="sxs-lookup"><span data-stu-id="bce50-131">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
- <span data-ttu-id="bce50-132">Non è possibile inserire sulla stessa riga una sequenza di continuazione di riga seguita da un commento.</span><span class="sxs-lookup"><span data-stu-id="bce50-132">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="bce50-133">È possibile aggiungere o rimuovere i simboli di commento per un blocco di codice selezionando una o più righe di codice e scegliendo il **Commento** ( ![ il Visual Basic pulsante commento in Visual Studio ](./media/comments-in-code/visual-basic-comment-button.gif) ) e rimuovere il **Commento** ( ![ il Visual Basic pulsante Rimuovi commento in Visual Studio. ](./media/comments-in-code/visual-basic-uncomment-button.gif) ) nella barra degli strumenti **modifica** .</span><span class="sxs-lookup"><span data-stu-id="bce50-133">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![The Visual Basic Comment button in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) and **Uncomment** (![The Visual Basic Uncomment button in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bce50-134">Per aggiungere commenti al codice è possibile anche inserire la parola chiave `REM` prima del testo.</span><span class="sxs-lookup"><span data-stu-id="bce50-134">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="bce50-135">Tuttavia, i `'` pulsanti simbolo e **Rimuovi** / **Commento** sono più semplici da utilizzare e richiedono meno spazio e memoria.</span><span class="sxs-lookup"><span data-stu-id="bce50-135">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce50-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bce50-136">See also</span></span>

- [<span data-ttu-id="bce50-137">Istinti di base-documentazione del codice con commenti XML</span><span class="sxs-lookup"><span data-stu-id="bce50-137">Basic Instincts - Documenting Your Code With XML Comments</span></span>](https://docs.microsoft.com/archive/msdn-magazine/2009/may/documenting-your-code-with-xml-comments)
- [<span data-ttu-id="bce50-138">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="bce50-138">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)
- [<span data-ttu-id="bce50-139">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="bce50-139">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)
- [<span data-ttu-id="bce50-140">Struttura del programma e convenzioni del codice</span><span class="sxs-lookup"><span data-stu-id="bce50-140">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="bce50-141">Istruzione REM</span><span class="sxs-lookup"><span data-stu-id="bce50-141">REM Statement</span></span>](../../language-reference/statements/rem-statement.md)
