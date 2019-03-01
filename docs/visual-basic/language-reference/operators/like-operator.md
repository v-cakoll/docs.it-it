---
title: Like (operatore) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: f26cadc4f64626f2a79eb37352f4906cea9092bb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979928"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="13bea-102">Like (operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13bea-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="13bea-103">Confronta una stringa con un modello.</span><span class="sxs-lookup"><span data-stu-id="13bea-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="13bea-104">Il `Like` operatore non è attualmente supportato nei progetti .NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="13bea-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="13bea-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13bea-105">Syntax</span></span>  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="13bea-106">Parti</span><span class="sxs-lookup"><span data-stu-id="13bea-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="13bea-107">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="13bea-107">Required.</span></span> <span data-ttu-id="13bea-108">Qualsiasi `Boolean` variabile.</span><span class="sxs-lookup"><span data-stu-id="13bea-108">Any `Boolean` variable.</span></span> <span data-ttu-id="13bea-109">Il risultato è un `Boolean` valore che indica se il `string` soddisfa le `pattern`.</span><span class="sxs-lookup"><span data-stu-id="13bea-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="13bea-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="13bea-110">Required.</span></span> <span data-ttu-id="13bea-111">Qualsiasi espressione `String` .</span><span class="sxs-lookup"><span data-stu-id="13bea-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="13bea-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="13bea-112">Required.</span></span> <span data-ttu-id="13bea-113">Qualsiasi `String` espressione conforme alle convenzioni sui criteri di ricerca descritti in "Osservazioni".</span><span class="sxs-lookup"><span data-stu-id="13bea-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13bea-114">Note</span><span class="sxs-lookup"><span data-stu-id="13bea-114">Remarks</span></span>  
 <span data-ttu-id="13bea-115">Se il valore in `string` soddisfa i `pattern`, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="13bea-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="13bea-116">Se la stringa non soddisfa il criterio `result` è `False`.</span><span class="sxs-lookup"><span data-stu-id="13bea-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="13bea-117">Se entrambe `string` e `pattern` sono stringhe vuote, il risultato è `True`.</span><span class="sxs-lookup"><span data-stu-id="13bea-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="13bea-118">Metodo di confronto</span><span class="sxs-lookup"><span data-stu-id="13bea-118">Comparison Method</span></span>  
 <span data-ttu-id="13bea-119">Il comportamento dei `Like` operatore dipende il [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="13bea-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="13bea-120">Il metodo di confronto stringhe predefinito per ogni file di origine è `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="13bea-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="13bea-121">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="13bea-121">Pattern Options</span></span>  
 <span data-ttu-id="13bea-122">Criteri predefiniti di ricerca fornisce uno strumento versatile per confronti tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="13bea-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="13bea-123">La funzionalità criteri di ricerca consentono di associare ogni carattere `string` su un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="13bea-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="13bea-124">La tabella seguente mostra i caratteri consentiti in `pattern` e le relative corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="13bea-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="13bea-125">Caratteri in `pattern`</span><span class="sxs-lookup"><span data-stu-id="13bea-125">Characters in `pattern`</span></span>|<span data-ttu-id="13bea-126">Corrispondenze in `string`</span><span class="sxs-lookup"><span data-stu-id="13bea-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="13bea-127">Qualsiasi carattere singolo</span><span class="sxs-lookup"><span data-stu-id="13bea-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="13bea-128">Zero o più caratteri</span><span class="sxs-lookup"><span data-stu-id="13bea-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="13bea-129">Qualsiasi cifra (0-9)</span><span class="sxs-lookup"><span data-stu-id="13bea-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="13bea-130">Qualsiasi carattere singolo in `charlist`</span><span class="sxs-lookup"><span data-stu-id="13bea-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="13bea-131">Qualsiasi carattere singolo non incluso `charlist`</span><span class="sxs-lookup"><span data-stu-id="13bea-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="13bea-132">Elenchi di carattere</span><span class="sxs-lookup"><span data-stu-id="13bea-132">Character Lists</span></span>  
 <span data-ttu-id="13bea-133">Un gruppo di uno o più caratteri (`charlist`) racchiusi tra parentesi quadre (`[ ]`) possono essere utilizzati per associare qualsiasi carattere singolo in `string` e può includere codice quasi qualsiasi carattere, comprese le cifre.</span><span class="sxs-lookup"><span data-stu-id="13bea-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="13bea-134">Un punto esclamativo (`!`) all'inizio del `charlist` significa che una corrispondenza viene eseguita se qualsiasi carattere tranne i caratteri nella `charlist` si trova `string`.</span><span class="sxs-lookup"><span data-stu-id="13bea-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="13bea-135">Quando usato all'esterno delle parentesi quadre, punto esclamativo corrisponde a se stesso.</span><span class="sxs-lookup"><span data-stu-id="13bea-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="13bea-136">Caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="13bea-136">Special Characters</span></span>  
 <span data-ttu-id="13bea-137">Per la corrispondenza tra parentesi quadre sinistra i caratteri speciali (`[`), punto interrogativo (`?`), simbolo di cancelletto (`#`) e l'asterisco (`*`), racchiuderli tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="13bea-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="13bea-138">La parentesi quadra chiusa (`]`) non può essere usato all'interno di un gruppo per stabilire una corrispondenza, ma può essere usato all'esterno di un gruppo come un singolo carattere.</span><span class="sxs-lookup"><span data-stu-id="13bea-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="13bea-139">La sequenza di caratteri `[]` viene considerato una stringa di lunghezza zero (`""`).</span><span class="sxs-lookup"><span data-stu-id="13bea-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="13bea-140">Tuttavia, non può far parte di un elenco di caratteri racchiusi tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="13bea-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="13bea-141">Se si desidera verificare se una posizione nella `string` contiene uno di un gruppo di caratteri o nessun carattere, è possibile usare `Like` due volte.</span><span class="sxs-lookup"><span data-stu-id="13bea-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="13bea-142">Per un esempio, vedere [Procedura: Confrontare una stringa con un modello](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="13bea-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="13bea-143">Intervalli di caratteri</span><span class="sxs-lookup"><span data-stu-id="13bea-143">Character Ranges</span></span>  
 <span data-ttu-id="13bea-144">Tramite un segno meno (`–`) per separare i limiti inferiore e superiore dell'intervallo, `charlist` può specificare un intervallo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="13bea-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="13bea-145">Ad esempio, `[A–Z]` produce una corrispondenza, se la posizione corrispondente `string` contiene un qualsiasi carattere compreso nell'intervallo `A`–`Z`, e `[!H–L]` produce una corrispondenza, se la posizione corrispondente contiene un qualsiasi carattere compreso nell'intervallo `H`–`L`.</span><span class="sxs-lookup"><span data-stu-id="13bea-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="13bea-146">Quando si specifica un intervallo di caratteri, è necessario specificarle nell'ordine crescente, vale a dire, dal minore al maggiore.</span><span class="sxs-lookup"><span data-stu-id="13bea-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="13bea-147">Pertanto `[A–Z]` è un modello valido, ma `[Z–A]` non.</span><span class="sxs-lookup"><span data-stu-id="13bea-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="13bea-148">Più intervalli di caratteri</span><span class="sxs-lookup"><span data-stu-id="13bea-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="13bea-149">Per specificare più intervalli per la stessa posizione del carattere, inserirli all'interno delle parentesi stesse senza delimitatori.</span><span class="sxs-lookup"><span data-stu-id="13bea-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="13bea-150">Ad esempio, `[A–CX–Z]` produce una corrispondenza, se la posizione corrispondente `string` contiene un qualsiasi carattere compreso nell'intervallo `A`–`C` o all'intervallo `X`–`Z`.</span><span class="sxs-lookup"><span data-stu-id="13bea-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="13bea-151">Utilizzo del trattino</span><span class="sxs-lookup"><span data-stu-id="13bea-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="13bea-152">Un segno meno (`–`) possono essere visualizzati all'inizio (dopo un punto esclamativo, se presente) o alla fine di `charlist` per stabilire una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="13bea-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="13bea-153">In altre posizioni, il trattino identifica un intervallo di caratteri delimitata dai caratteri ai lati del segno meno.</span><span class="sxs-lookup"><span data-stu-id="13bea-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="13bea-154">Sequenza di ordinamento</span><span class="sxs-lookup"><span data-stu-id="13bea-154">Collating Sequence</span></span>  
 <span data-ttu-id="13bea-155">Il significato di un intervallo specifico dipende dal carattere di ordinamento in fase di esecuzione, come determinato dalla `Option Compare` e le impostazioni locali del sistema in cui viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="13bea-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="13bea-156">Con `Option Compare Binary`, l'intervallo `[A–E]` corrisponda `A`, `B`, `C`, `D`, e `E`.</span><span class="sxs-lookup"><span data-stu-id="13bea-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="13bea-157">Con `Option Compare Text`, `[A–E]` corrisponda `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, e `e`.</span><span class="sxs-lookup"><span data-stu-id="13bea-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="13bea-158">L'intervallo corrisponde `Ê` o `ê` perché accenti collate dopo i caratteri non accentate nell'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="13bea-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="13bea-159">Digraph caratteri</span><span class="sxs-lookup"><span data-stu-id="13bea-159">Digraph Characters</span></span>  
 <span data-ttu-id="13bea-160">In alcune lingue, sono presenti caratteri alfabetici che rappresentano due caratteri distinti.</span><span class="sxs-lookup"><span data-stu-id="13bea-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="13bea-161">Ad esempio, diversi linguaggi di usano il carattere `æ` per rappresentare i caratteri `a` e `e` quando vengono visualizzati insieme.</span><span class="sxs-lookup"><span data-stu-id="13bea-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="13bea-162">Il `Like` operatore riconosce che il singolo carattere digraph e i due caratteri singoli sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="13bea-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="13bea-163">Quando una lingua che usa un carattere digraph viene specificata nelle impostazioni locali del sistema, un'occorrenza del carattere in uno singolo digraph `pattern` o `string` corrisponde alla sequenza di due caratteri equivalente in altra stringa.</span><span class="sxs-lookup"><span data-stu-id="13bea-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="13bea-164">Analogamente, un carattere di digraph nella `pattern` racchiusi tra parentesi quadre (di per sé, in un elenco o in un intervallo) corrisponde alla sequenza di due caratteri equivalente in `string`.</span><span class="sxs-lookup"><span data-stu-id="13bea-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="13bea-165">Overload</span><span class="sxs-lookup"><span data-stu-id="13bea-165">Overloading</span></span>  
 <span data-ttu-id="13bea-166">Il `Like` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="13bea-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="13bea-167">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="13bea-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="13bea-168">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="13bea-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13bea-169">Esempio</span><span class="sxs-lookup"><span data-stu-id="13bea-169">Example</span></span>  
 <span data-ttu-id="13bea-170">Questo esempio viene usato il `Like` operatore per confrontare le stringhe in vari modelli.</span><span class="sxs-lookup"><span data-stu-id="13bea-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="13bea-171">I risultati vengono inseriti in un `Boolean` variabile che indica se ogni stringa soddisfa il modello.</span><span class="sxs-lookup"><span data-stu-id="13bea-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="13bea-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13bea-172">See also</span></span>
- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="13bea-173">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="13bea-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="13bea-174">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13bea-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="13bea-175">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="13bea-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="13bea-176">Istruzione Option Compare</span><span class="sxs-lookup"><span data-stu-id="13bea-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="13bea-177">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="13bea-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="13bea-178">Procedura: Confrontare una stringa con un modello</span><span class="sxs-lookup"><span data-stu-id="13bea-178">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
