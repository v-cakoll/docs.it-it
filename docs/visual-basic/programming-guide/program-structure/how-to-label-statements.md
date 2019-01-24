---
title: 'Procedura: Etichetta istruzioni (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 00a08bd3bd1f866cec883b6591b03ebd9d858b90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552260"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="9bf0a-102">Procedura: Etichetta istruzioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bf0a-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="9bf0a-103">Blocchi di istruzioni sono costituiti da righe di codice delimitati da punti.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="9bf0a-104">Righe di codice preceduto da una stringa o numero intero di identificazione si dice che trovano *etichettato*.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="9bf0a-105">Le etichette di istruzione vengono utilizzate per contrassegnare una riga di codice per facilitarne l'identificazione per l'uso con le istruzioni, ad esempio `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="9bf0a-106">Le etichette possono essere identificatori Visual Basic validi, ad esempio quelli che identificano gli elementi di programmazione, o i valori letterali integer.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="9bf0a-107">Un'etichetta deve essere visualizzati all'inizio di una riga di codice sorgente e deve essere seguita da due punti, indipendentemente dal fatto che è seguito da un'istruzione nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="9bf0a-108">Il compilatore identifica le etichette, controllare se l'inizio della riga corrisponde a qualsiasi identificatore già definito.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="9bf0a-109">In caso contrario, il compilatore presuppone che sia un'etichetta.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="9bf0a-110">Le etichette sono proprio spazio di dichiarazione e non interferiscono con altri identificatori.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="9bf0a-111">Ambito dell'etichetta è il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="9bf0a-112">Dichiarazione di etichetta ha la precedenza in qualsiasi situazione ambigua.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bf0a-113">Le etichette possono essere utilizzate solo in istruzioni eseguibili nei metodi.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="9bf0a-114">Per assegnare un'etichetta di una riga di codice</span><span class="sxs-lookup"><span data-stu-id="9bf0a-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="9bf0a-115">Inserire un identificatore, seguito da due punti, all'inizio della riga di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="9bf0a-116">Ad esempio, le righe di codice seguenti sono contrassegnate con `Jump` e `120`, rispettivamente:</span><span class="sxs-lookup"><span data-stu-id="9bf0a-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9bf0a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bf0a-117">See also</span></span>
- [<span data-ttu-id="9bf0a-118">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="9bf0a-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="9bf0a-119">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="9bf0a-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="9bf0a-120">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="9bf0a-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
