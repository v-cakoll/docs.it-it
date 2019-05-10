---
title: 'Procedura: Confrontare una stringa con un modello (Visual Basic)'
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
ms.openlocfilehash: e5eb6bd5b5e7b2f0c3692c0fa2431a0b8f295299
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649720"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="21c4f-102">Procedura: Confrontare una stringa con un modello (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21c4f-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="21c4f-103">Se si desidera determinare se un'espressione del [tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md) soddisfa un modello, è possibile utilizzare il [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="21c4f-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="21c4f-104">`Like` accetta due operandi.</span><span class="sxs-lookup"><span data-stu-id="21c4f-104">`Like` takes two operands.</span></span> <span data-ttu-id="21c4f-105">L'operando sinistro è un'espressione stringa e l'operando destro è una stringa che contiene il modello da utilizzare per la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="21c4f-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="21c4f-106">`Like` Restituisce un `Boolean` valore che indica se l'espressione stringa soddisfa il modello.</span><span class="sxs-lookup"><span data-stu-id="21c4f-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="21c4f-107">È possibile associare ogni carattere dell'espressione di stringa con un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="21c4f-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="21c4f-108">Le posizioni delle specifiche nella stringa di modello corrispondano alle posizioni dei caratteri da cui trovare una corrispondenza nell'espressione stringa.</span><span class="sxs-lookup"><span data-stu-id="21c4f-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="21c4f-109">Per confrontare un carattere incluso nell'espressione di stringa con un carattere specifico</span><span class="sxs-lookup"><span data-stu-id="21c4f-109">To match a character in the string expression against a specific character</span></span>  
  
- <span data-ttu-id="21c4f-110">Inserire il carattere specifico direttamente nella stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="21c4f-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="21c4f-111">Alcuni caratteri speciali devono essere racchiusi tra parentesi quadre (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="21c4f-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="21c4f-112">Per altre informazioni, vedere [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="21c4f-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="21c4f-113">Nell'esempio seguente viene verificato se `myString` è costituito da esattamente il carattere singolo `H`.</span><span class="sxs-lookup"><span data-stu-id="21c4f-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="21c4f-114">Per confrontare un carattere incluso nell'espressione di stringa con un carattere jolly</span><span class="sxs-lookup"><span data-stu-id="21c4f-114">To match a character in the string expression against a wildcard character</span></span>  
  
- <span data-ttu-id="21c4f-115">Inserire un punto interrogativo (`?`) nella stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="21c4f-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="21c4f-116">Qualsiasi carattere valido in questa posizione determina una corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="21c4f-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="21c4f-117">Nell'esempio seguente viene verificato se `myString` costituita dal carattere singolo `W` seguita da due caratteri di tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="21c4f-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="21c4f-118">Per confrontare un carattere nell'espressione stringa rispetto a un elenco di caratteri</span><span class="sxs-lookup"><span data-stu-id="21c4f-118">To match a character in the string expression against a list of characters</span></span>  
  
- <span data-ttu-id="21c4f-119">Inserire le parentesi (`[ ]`) nella stringa di modello e all'interno delle parentesi inserire l'elenco dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="21c4f-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="21c4f-120">Non separare i caratteri con virgole o qualsiasi altro separatore.</span><span class="sxs-lookup"><span data-stu-id="21c4f-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="21c4f-121">Qualsiasi carattere singolo nell'elenco determina una corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="21c4f-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="21c4f-122">Nell'esempio seguente viene verificato se `myString` è costituito da qualsiasi carattere valido seguiti da un solo i caratteri `A`, `C`, o `E`.</span><span class="sxs-lookup"><span data-stu-id="21c4f-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     <span data-ttu-id="21c4f-123">Si noti che questa corrispondenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="21c4f-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="21c4f-124">Per confrontare un carattere incluso nell'espressione di stringa con un intervallo di caratteri</span><span class="sxs-lookup"><span data-stu-id="21c4f-124">To match a character in the string expression against a range of characters</span></span>  
  
- <span data-ttu-id="21c4f-125">Inserire le parentesi (`[ ]`) nella stringa di modello e racchiudere tra parentesi i minimo e massimo di caratteri nell'intervallo, separati da un trattino (`–`).</span><span class="sxs-lookup"><span data-stu-id="21c4f-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="21c4f-126">Qualsiasi carattere singolo compreso nell'intervallo determina una corrispondenza corretta.</span><span class="sxs-lookup"><span data-stu-id="21c4f-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="21c4f-127">Nell'esempio seguente viene verificato se `myString` è costituito da caratteri `num` seguita da esattamente uno dei caratteri `i`, `j`, `k`, `l`, `m`, o `n`.</span><span class="sxs-lookup"><span data-stu-id="21c4f-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     <span data-ttu-id="21c4f-128">Si noti che questa corrispondenza tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="21c4f-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="21c4f-129">Confronto di stringhe vuote</span><span class="sxs-lookup"><span data-stu-id="21c4f-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="21c4f-130">`Like` considera la sequenza `[]` come una stringa di lunghezza zero (`""`).</span><span class="sxs-lookup"><span data-stu-id="21c4f-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="21c4f-131">È possibile usare `[]` per verificare se l'espressione intera stringa è vuota, ma non può essere utilizzato per verificare se una determinata posizione nell'espressione stringa è vuota.</span><span class="sxs-lookup"><span data-stu-id="21c4f-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="21c4f-132">Se una posizione vuota è una delle opzioni è necessario per il test, è possibile usare `Like` più volte.</span><span class="sxs-lookup"><span data-stu-id="21c4f-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="21c4f-133">Per confrontare un carattere nell'espressione stringa rispetto a un elenco di caratteri o nessun carattere</span><span class="sxs-lookup"><span data-stu-id="21c4f-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1. <span data-ttu-id="21c4f-134">Chiamare il `Like` operatore due volte sulla stessa espressione di tipo string e connettere le due chiamate con il [operatore o](../../../../visual-basic/language-reference/operators/or-operator.md) o il [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="21c4f-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2. <span data-ttu-id="21c4f-135">Nella stringa di modello per i primi `Like` clausola, includere l'elenco di caratteri racchiusi tra parentesi quadre (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="21c4f-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3. <span data-ttu-id="21c4f-136">Nella stringa di modello per il secondo `Like` clausola, non inserire qualsiasi carattere in corrispondenza della posizione in questione.</span><span class="sxs-lookup"><span data-stu-id="21c4f-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="21c4f-137">L'esempio seguente verifica il numero di telefono a 7 cifre `phoneNum` per esattamente tre cifre numeriche, seguita da uno spazio, un segno meno (`–`), un periodo (`.`), o nessun carattere affatto, seguita da quattro cifre.</span><span class="sxs-lookup"><span data-stu-id="21c4f-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="21c4f-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21c4f-138">See also</span></span>

- [<span data-ttu-id="21c4f-139">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="21c4f-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="21c4f-140">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="21c4f-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="21c4f-141">Operatore Like</span><span class="sxs-lookup"><span data-stu-id="21c4f-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="21c4f-142">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="21c4f-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
