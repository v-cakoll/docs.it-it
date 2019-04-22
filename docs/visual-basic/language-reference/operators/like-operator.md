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
ms.openlocfilehash: 38e56b8c0ec6bab89052ee42a2cd9c24053c658e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835700"
---
# <a name="like-operator-visual-basic"></a>Like (operatore) (Visual Basic)
Confronta una stringa con un modello.  

> [!IMPORTANT]
> Il `Like` operatore non è attualmente supportato nei progetti .NET Core e .NET Standard.

## <a name="syntax"></a>Sintassi  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` variabile. Il risultato è un `Boolean` valore che indica se il `string` soddisfa le `pattern`.  
  
 `string`  
 Obbligatorio. Qualsiasi espressione `String` .  
  
 `pattern`  
 Obbligatorio. Qualsiasi `String` espressione conforme alle convenzioni sui criteri di ricerca descritti in "Osservazioni".  
  
## <a name="remarks"></a>Note  
 Se il valore in `string` soddisfa i `pattern`, `result` è `True`. Se la stringa non soddisfa il criterio `result` è `False`. Se entrambe `string` e `pattern` sono stringhe vuote, il risultato è `True`.  
  
## <a name="comparison-method"></a>Metodo di confronto  
 Il comportamento dei `Like` operatore dipende il [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md). Il metodo di confronto stringhe predefinito per ogni file di origine è `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Opzioni del modello  
 Criteri predefiniti di ricerca fornisce uno strumento versatile per confronti tra stringhe. La funzionalità criteri di ricerca consentono di associare ogni carattere `string` su un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri. La tabella seguente mostra i caratteri consentiti in `pattern` e le relative corrispondenze.  
  
|Caratteri in `pattern`|Corrispondenze in `string`|  
|-----------------------------|-------------------------|  
|`?`|Qualsiasi carattere singolo|  
|`*`|Zero o più caratteri|  
|`#`|Qualsiasi cifra (0-9)|  
|`[charlist]`|Qualsiasi carattere singolo in `charlist`|  
|`[!charlist]`|Qualsiasi carattere singolo non incluso `charlist`|  
  
## <a name="character-lists"></a>Elenchi di carattere  
 Un gruppo di uno o più caratteri (`charlist`) racchiusi tra parentesi quadre (`[ ]`) possono essere utilizzati per associare qualsiasi carattere singolo in `string` e può includere codice quasi qualsiasi carattere, comprese le cifre.  
  
 Un punto esclamativo (`!`) all'inizio del `charlist` significa che una corrispondenza viene eseguita se qualsiasi carattere tranne i caratteri nella `charlist` si trova `string`. Quando usato all'esterno delle parentesi quadre, punto esclamativo corrisponde a se stesso.  
  
## <a name="special-characters"></a>Caratteri speciali  
 Per la corrispondenza tra parentesi quadre sinistra i caratteri speciali (`[`), punto interrogativo (`?`), simbolo di cancelletto (`#`) e l'asterisco (`*`), racchiuderli tra parentesi quadre. La parentesi quadra chiusa (`]`) non può essere usato all'interno di un gruppo per stabilire una corrispondenza, ma può essere usato all'esterno di un gruppo come un singolo carattere.  
  
 La sequenza di caratteri `[]` viene considerato una stringa di lunghezza zero (`""`). Tuttavia, non può far parte di un elenco di caratteri racchiusi tra parentesi quadre. Se si desidera verificare se una posizione nella `string` contiene uno di un gruppo di caratteri o nessun carattere, è possibile usare `Like` due volte. Per un esempio, vedere [Procedura: Confrontare una stringa con un modello](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Intervalli di caratteri  
 Tramite un segno meno (`–`) per separare i limiti inferiore e superiore dell'intervallo, `charlist` può specificare un intervallo di caratteri. Ad esempio, `[A–Z]` produce una corrispondenza, se la posizione corrispondente `string` contiene un qualsiasi carattere compreso nell'intervallo `A`–`Z`, e `[!H–L]` produce una corrispondenza, se la posizione corrispondente contiene un qualsiasi carattere compreso nell'intervallo `H`–`L`.  
  
 Quando si specifica un intervallo di caratteri, è necessario specificarle nell'ordine crescente, vale a dire, dal minore al maggiore. Pertanto `[A–Z]` è un modello valido, ma `[Z–A]` non.  
  
### <a name="multiple-character-ranges"></a>Più intervalli di caratteri  
 Per specificare più intervalli per la stessa posizione del carattere, inserirli all'interno delle parentesi stesse senza delimitatori. Ad esempio, `[A–CX–Z]` produce una corrispondenza, se la posizione corrispondente `string` contiene un qualsiasi carattere compreso nell'intervallo `A`–`C` o all'intervallo `X`–`Z`.  
  
### <a name="usage-of-the-hyphen"></a>Utilizzo del trattino  
 Un segno meno (`–`) possono essere visualizzati all'inizio (dopo un punto esclamativo, se presente) o alla fine di `charlist` per stabilire una corrispondenza. In altre posizioni, il trattino identifica un intervallo di caratteri delimitata dai caratteri ai lati del segno meno.  
  
## <a name="collating-sequence"></a>Sequenza di ordinamento  
 Il significato di un intervallo specifico dipende dal carattere di ordinamento in fase di esecuzione, come determinato dalla `Option Compare` e le impostazioni locali del sistema in cui viene eseguito il codice. Con `Option Compare Binary`, l'intervallo `[A–E]` corrisponda `A`, `B`, `C`, `D`, e `E`. Con `Option Compare Text`, `[A–E]` corrisponda `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, e `e`. L'intervallo corrisponde `Ê` o `ê` perché accenti collate dopo i caratteri non accentate nell'ordinamento.  
  
## <a name="digraph-characters"></a>Digraph caratteri  
 In alcune lingue, sono presenti caratteri alfabetici che rappresentano due caratteri distinti. Ad esempio, diversi linguaggi di usano il carattere `æ` per rappresentare i caratteri `a` e `e` quando vengono visualizzati insieme. Il `Like` operatore riconosce che il singolo carattere digraph e i due caratteri singoli sono equivalenti.  
  
 Quando una lingua che usa un carattere digraph viene specificata nelle impostazioni locali del sistema, un'occorrenza del carattere in uno singolo digraph `pattern` o `string` corrisponde alla sequenza di due caratteri equivalente in altra stringa. Analogamente, un carattere di digraph nella `pattern` racchiusi tra parentesi quadre (di per sé, in un elenco o in un intervallo) corrisponde alla sequenza di due caratteri equivalente in `string`.  
  
## <a name="overloading"></a>Overload  
 Il `Like` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `Like` operatore per confrontare le stringhe in vari modelli. I risultati vengono inseriti in un `Boolean` variabile che indica se ogni stringa soddisfa il modello.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Procedura: Confrontare una stringa con un modello](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
