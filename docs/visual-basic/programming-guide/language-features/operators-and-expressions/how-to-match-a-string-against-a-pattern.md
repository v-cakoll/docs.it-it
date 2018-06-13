---
title: 'Procedura: confrontare una stringa con un modello (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: aef378bfc32d6deff431a2caac1261a6cd7520c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655212"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="0ce68-102">Procedura: confrontare una stringa con un modello (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ce68-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="0ce68-103">Se si desidera determinare se un'espressione del [tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md) soddisfa un modello, è possibile utilizzare il [operatore Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0ce68-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="0ce68-104">`Like` accetta due operandi.</span><span class="sxs-lookup"><span data-stu-id="0ce68-104">`Like` takes two operands.</span></span> <span data-ttu-id="0ce68-105">L'operando sinistro è un'espressione stringa e l'operando destro è una stringa contenente il modello da utilizzare per la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="0ce68-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="0ce68-106">`Like` Restituisce un `Boolean` valore che indica se l'espressione stringa soddisfa il criterio.</span><span class="sxs-lookup"><span data-stu-id="0ce68-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="0ce68-107">È possibile associare ogni carattere incluso nell'espressione stringa con un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="0ce68-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="0ce68-108">Le posizioni delle specifiche nella stringa modello corrispondono alle posizioni dei caratteri per cui trovare una corrispondenza nell'espressione stringa.</span><span class="sxs-lookup"><span data-stu-id="0ce68-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="0ce68-109">Per confrontare un carattere incluso nell'espressione stringa con un carattere specifico</span><span class="sxs-lookup"><span data-stu-id="0ce68-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="0ce68-110">Inserire il carattere specifico direttamente nella stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="0ce68-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="0ce68-111">Alcuni caratteri speciali devono essere racchiusi tra parentesi (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="0ce68-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="0ce68-112">Per ulteriori informazioni, vedere [operatore Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0ce68-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="0ce68-113">Nell'esempio seguente viene verificato se `myString` costituito esattamente il singolo carattere `H`.</span><span class="sxs-lookup"><span data-stu-id="0ce68-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="0ce68-114">Per confrontare un carattere incluso nell'espressione stringa con un carattere jolly</span><span class="sxs-lookup"><span data-stu-id="0ce68-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="0ce68-115">Inserire un punto interrogativo (`?`) nella stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="0ce68-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="0ce68-116">Qualsiasi carattere valido in questa posizione determina una corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="0ce68-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="0ce68-117">Nell'esempio seguente viene verificato se `myString` costituito dal singolo carattere `W` seguita da due caratteri di tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="0ce68-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="0ce68-118">Per confrontare un carattere nell'espressione stringa in un elenco di caratteri</span><span class="sxs-lookup"><span data-stu-id="0ce68-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="0ce68-119">Inserire le parentesi (`[ ]`) nella stringa di modello e all'interno delle parentesi inserire l'elenco dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="0ce68-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="0ce68-120">Non separare i caratteri con virgole o qualsiasi altro separatore.</span><span class="sxs-lookup"><span data-stu-id="0ce68-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="0ce68-121">Qualsiasi carattere singolo nell'elenco determina una corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="0ce68-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="0ce68-122">Nell'esempio seguente viene verificato se `myString` è costituito da qualsiasi carattere valido seguito da esattamente uno dei caratteri `A`, `C`, o `E`.</span><span class="sxs-lookup"><span data-stu-id="0ce68-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     <span data-ttu-id="0ce68-123">Si noti che questa corrispondenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0ce68-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="0ce68-124">Per confrontare un carattere incluso nell'espressione stringa con un intervallo di caratteri</span><span class="sxs-lookup"><span data-stu-id="0ce68-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="0ce68-125">Inserire le parentesi (`[ ]`) nella stringa di modello e racchiudere tra parentesi i caratteri minimo e massimo dell'intervallo, separati da un trattino (`–`).</span><span class="sxs-lookup"><span data-stu-id="0ce68-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="0ce68-126">Qualsiasi carattere singolo compreso nell'intervallo determina una corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="0ce68-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="0ce68-127">Nell'esempio seguente viene verificato se `myString` costituito dai caratteri `num` seguiti da un solo i caratteri `i`, `j`, `k`, `l`, `m`, o `n`.</span><span class="sxs-lookup"><span data-stu-id="0ce68-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     <span data-ttu-id="0ce68-128">Si noti che questa corrispondenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0ce68-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="0ce68-129">Confronto di stringhe vuote</span><span class="sxs-lookup"><span data-stu-id="0ce68-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="0ce68-130">`Like` considera la sequenza `[]` come una stringa di lunghezza zero (`""`).</span><span class="sxs-lookup"><span data-stu-id="0ce68-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="0ce68-131">È possibile utilizzare `[]` per verificare se l'intera espressione stringa è vuoto, ma non può essere utilizzato per verificare se una determinata posizione nell'espressione stringa è vuota.</span><span class="sxs-lookup"><span data-stu-id="0ce68-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="0ce68-132">Se una posizione vuota è una delle opzioni è necessario per il test, è possibile utilizzare `Like` più volte.</span><span class="sxs-lookup"><span data-stu-id="0ce68-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="0ce68-133">Per confrontare un carattere nell'espressione stringa in un elenco di caratteri o alcun carattere</span><span class="sxs-lookup"><span data-stu-id="0ce68-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1.  <span data-ttu-id="0ce68-134">Chiamare il `Like` operatore due volte nella stessa espressione di tipo string e connettere le due chiamate con il [operatore o](../../../../visual-basic/language-reference/operators/or-operator.md) o [OrElse (operatore)](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0ce68-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2.  <span data-ttu-id="0ce68-135">Nella stringa di modello per la prima `Like` clausola, includere l'elenco di caratteri racchiusi tra parentesi quadre (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="0ce68-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3.  <span data-ttu-id="0ce68-136">Nella stringa di modello per il secondo `Like` clausola, non inserire alcun carattere in corrispondenza della posizione in questione.</span><span class="sxs-lookup"><span data-stu-id="0ce68-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="0ce68-137">Nell'esempio seguente verifica il numero di telefono di sette cifre `phoneNum` per esattamente tre cifre numeriche, seguita da uno spazio, un trattino (`–`), un periodo (`.`), o nessun carattere, seguita da quattro cifre.</span><span class="sxs-lookup"><span data-stu-id="0ce68-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0ce68-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ce68-138">See Also</span></span>  
 [<span data-ttu-id="0ce68-139">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="0ce68-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="0ce68-140">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="0ce68-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="0ce68-141">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="0ce68-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="0ce68-142">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="0ce68-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
