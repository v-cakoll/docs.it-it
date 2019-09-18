---
title: 'Procedura: Istruzioni Label (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 9a5f2039716a18011cac3dfd9b011d5b3868c294
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054047"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="8aad2-102">Procedura: Istruzioni Label (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8aad2-102">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="8aad2-103">I blocchi di istruzioni sono costituiti da righe di codice delimitate da due punti.</span><span class="sxs-lookup"><span data-stu-id="8aad2-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="8aad2-104">Le righe di codice precedute da una stringa di identificazione o un numero intero sono *denominate etichettate*.</span><span class="sxs-lookup"><span data-stu-id="8aad2-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="8aad2-105">Le etichette di istruzione vengono utilizzate per contrassegnare una riga di codice per identificarla per l'utilizzo `On Error Goto`con istruzioni quali.</span><span class="sxs-lookup"><span data-stu-id="8aad2-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="8aad2-106">Le etichette possono essere identificatori Visual Basic validi, ad esempio quelli che identificano gli elementi di programmazione, o valori letterali integer.</span><span class="sxs-lookup"><span data-stu-id="8aad2-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="8aad2-107">Un'etichetta deve essere visualizzata all'inizio di una riga di codice sorgente e deve essere seguita da due punti, indipendentemente dal fatto che sia seguita da un'istruzione nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="8aad2-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="8aad2-108">Il compilatore identifica le etichette controllando se l'inizio della riga corrisponde a qualsiasi identificatore già definito.</span><span class="sxs-lookup"><span data-stu-id="8aad2-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="8aad2-109">In caso contrario, il compilatore presuppone che si tratta di un'etichetta.</span><span class="sxs-lookup"><span data-stu-id="8aad2-109">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="8aad2-110">Le etichette hanno uno spazio di dichiarazione e non interferiscono con altri identificatori.</span><span class="sxs-lookup"><span data-stu-id="8aad2-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="8aad2-111">L'ambito di un'etichetta è il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="8aad2-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="8aad2-112">La dichiarazione di etichetta ha la precedenza in qualsiasi situazione ambigua.</span><span class="sxs-lookup"><span data-stu-id="8aad2-112">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="8aad2-113">Le etichette possono essere utilizzate solo su istruzioni eseguibili all'interno di metodi.</span><span class="sxs-lookup"><span data-stu-id="8aad2-113">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="8aad2-114">Per etichettare una riga di codice</span><span class="sxs-lookup"><span data-stu-id="8aad2-114">To label a line of code</span></span>

<span data-ttu-id="8aad2-115">Posizionare un identificatore, seguito da due punti, all'inizio della riga del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="8aad2-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="8aad2-116">Ad esempio, le righe di codice seguenti sono etichettate rispettivamente `Jump` con `120`e:</span><span class="sxs-lookup"><span data-stu-id="8aad2-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="8aad2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aad2-117">See also</span></span>

- [<span data-ttu-id="8aad2-118">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="8aad2-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="8aad2-119">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="8aad2-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="8aad2-120">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="8aad2-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
