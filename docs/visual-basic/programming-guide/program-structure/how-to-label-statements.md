---
title: 'Procedura: etichettare le istruzioni (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 190ec9fc2392e6e4adae9b2b612edd69d73cedfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="354c8-102">Procedura: etichettare le istruzioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="354c8-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="354c8-103">Blocchi di istruzioni sono costituiti da righe di codice delimitati da virgola.</span><span class="sxs-lookup"><span data-stu-id="354c8-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="354c8-104">Righe di codice preceduto da una stringa di identificazione o intero rientrano *etichetta*.</span><span class="sxs-lookup"><span data-stu-id="354c8-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="354c8-105">Le etichette di istruzione vengono utilizzate per contrassegnare una riga di codice per facilitarne l'identificazione per l'utilizzo con le istruzioni, ad esempio `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="354c8-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="354c8-106">Le etichette possono essere identificatori validi di Visual Basic, ad esempio quelle che identificano gli elementi di programmazione, o valori letterali integer.</span><span class="sxs-lookup"><span data-stu-id="354c8-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="354c8-107">Un'etichetta deve trovarsi all'inizio di una riga di codice sorgente e deve essere seguita da due punti, indipendentemente dal fatto che è seguito da un'istruzione sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="354c8-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="354c8-108">Il compilatore identifica le etichette verificando se l'inizio della riga corrisponde a qualsiasi identificatore già definito.</span><span class="sxs-lookup"><span data-stu-id="354c8-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="354c8-109">In caso contrario, il compilatore presuppone che sia un'etichetta.</span><span class="sxs-lookup"><span data-stu-id="354c8-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="354c8-110">Le etichette sono proprio spazio di dichiarazione e non interferiscono con altri identificatori.</span><span class="sxs-lookup"><span data-stu-id="354c8-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="354c8-111">Ambito di un'etichetta è il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="354c8-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="354c8-112">Dichiarazione di etichetta ha la precedenza in caso di ambiguità.</span><span class="sxs-lookup"><span data-stu-id="354c8-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="354c8-113">Le etichette possono essere utilizzate solo in istruzioni eseguibili all'interno di metodi.</span><span class="sxs-lookup"><span data-stu-id="354c8-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="354c8-114">Per assegnare un'etichetta di una riga di codice</span><span class="sxs-lookup"><span data-stu-id="354c8-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="354c8-115">Inserire un identificatore, seguito da due punti, all'inizio della riga di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="354c8-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="354c8-116">Ad esempio, le righe di codice seguente vengono etichettate con `Jump` e `120`, rispettivamente:</span><span class="sxs-lookup"><span data-stu-id="354c8-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="354c8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="354c8-117">See Also</span></span>  
 [<span data-ttu-id="354c8-118">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="354c8-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="354c8-119">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="354c8-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="354c8-120">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="354c8-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
