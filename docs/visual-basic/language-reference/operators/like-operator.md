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
ms.openlocfilehash: 795ecc2e80d57af29ccd50c50d2dd209c6425e40
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701128"
---
# <a name="like-operator-visual-basic"></a>Like (operatore) (Visual Basic)
Confronta una stringa con un modello.  

> [!IMPORTANT]
> L'operatore `Like` non è attualmente supportato nei progetti .NET Core e .NET Standard.

## <a name="syntax"></a>Sintassi  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi variabile `Boolean`. Il risultato è un valore `Boolean` che indica se il `string` soddisfa la `pattern`.  
  
 `string`  
 Obbligatorio. Qualsiasi espressione `String` .  
  
 `pattern`  
 Obbligatorio. Qualsiasi espressione `String` conforme alle convenzioni dei criteri di ricerca descritte in "osservazioni".  
  
## <a name="remarks"></a>Note  
 Se il valore in `string` soddisfa il modello contenuto in `pattern`, `result` è `True`. Se la stringa non soddisfa il criterio, `result` è `False`. Se entrambe `string` e `pattern` sono stringhe vuote, il risultato sarà `True`.  
  
## <a name="comparison-method"></a>Metodo di confronto  
 Il comportamento dell'operatore `Like` dipende dall' [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md). Il metodo di confronto tra stringhe predefinito per ogni file di origine è `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Opzioni modello  
 Criteri di ricerca predefiniti fornisce uno strumento versatile per i confronti tra stringhe. Le funzionalità dei criteri di ricerca consentono di associare ogni carattere in `string` a un carattere specifico, a un carattere jolly, a un elenco di caratteri o a un intervallo di caratteri. Nella tabella seguente vengono illustrati i caratteri consentiti in `pattern` e le relative corrispondenze.  
  
|Caratteri in `pattern`|Corrispondenze in `string`|  
|-----------------------------|-------------------------|  
|`?`|Qualsiasi carattere singolo|  
|`*`|Zero o più caratteri|  
|`#`|Qualsiasi cifra singola (0-9)|  
|`[charlist]`|Qualsiasi carattere singolo in `charlist`|  
|`[!charlist]`|Qualsiasi carattere singolo non presente in `charlist`|  
  
## <a name="character-lists"></a>Elenchi di caratteri  
 Un gruppo di uno o più caratteri (`charlist`) racchiusi tra parentesi quadre (`[ ]`) può essere usato per trovare la corrispondenza con qualsiasi carattere singolo in `string` e può includere quasi tutti i codici carattere, incluse le cifre.  
  
 Un punto esclamativo (`!`) all'inizio di `charlist` indica che viene eseguita una corrispondenza se viene trovato un carattere qualsiasi, ad eccezione dei caratteri in `charlist`, in `string`. Quando viene usato all'esterno delle parentesi quadre, il punto esclamativo corrisponde a se stesso.  
  
## <a name="special-characters"></a>Caratteri speciali  
 Per trovare la corrispondenza con la parentesi quadra aperta (`[`), il punto interrogativo (`?`), il simbolo di cancelletto (`#`) e l'asterisco (`*`), racchiuderli tra parentesi quadre. La parentesi quadra chiusa (`]`) non può essere usata all'interno di un gruppo per trovare la corrispondenza, ma può essere usata all'esterno di un gruppo come singolo carattere.  
  
 La sequenza di caratteri `[]` è considerata una stringa di lunghezza zero (`""`). Tuttavia, non può far parte di un elenco di caratteri racchiuso tra parentesi quadre. Se si desidera controllare se una posizione in `string` contiene uno di un gruppo di caratteri o nessun carattere, è possibile utilizzare `Like` due volte. Per un esempio, vedere [Procedura: Trovare la corrispondenza di una stringa con un criterio @ no__t-0.  
  
## <a name="character-ranges"></a>Intervalli di caratteri  
 Utilizzando un trattino (`–`) per separare i limiti inferiore e superiore dell'intervallo, `charlist` può specificare un intervallo di caratteri. Ad esempio, `[A–Z]` restituisce una corrispondenza se la posizione del carattere corrispondente in `string` contiene un carattere compreso nell'intervallo `A`-`Z` e `[!H–L]` comporta una corrispondenza se la posizione del carattere corrispondente contiene un carattere esterno intervallo `H` – `L`.  
  
 Quando si specifica un intervallo di caratteri, questi devono essere visualizzati in ordine crescente, ovvero dal più basso al più alto. Pertanto, `[A–Z]` è un modello valido, ma `[Z–A]` non lo è.  
  
### <a name="multiple-character-ranges"></a>Più intervalli di caratteri  
 Per specificare più intervalli per la stessa posizione del carattere, inserirli all'interno delle stesse parentesi quadre senza delimitatori. Ad esempio, `[A–CX–Z]` restituisce una corrispondenza se la posizione del carattere corrispondente in `string` contiene qualsiasi carattere compreso nell'intervallo `A`-`C` o nell'intervallo `X` – `Z`.  
  
### <a name="usage-of-the-hyphen"></a>Utilizzo del trattino  
 Un trattino (`–`) può apparire all'inizio (dopo un punto esclamativo, se presente) o alla fine di `charlist` per corrispondere a se stesso. In qualsiasi altra posizione, il segno meno identifica un intervallo di caratteri delimitati dai caratteri su entrambi i lati del segno meno.  
  
## <a name="collating-sequence"></a>Sequenza di fascicolazione  
 Il significato di un intervallo specificato dipende dall'ordinamento dei caratteri in fase di esecuzione, come determinato da `Option Compare` e dalle impostazioni locali del sistema in cui è in esecuzione il codice. Con `Option Compare Binary`, l'intervallo `[A–E]` corrisponde `A`, `B`, `C`, `D` e `E`. Con `Option Compare Text`, `[A–E]` corrisponde `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, 0, 1, 2 e 3. L'intervallo non corrisponde a `Ê` o `ê` perché i caratteri accentati vengono ordinati dopo i caratteri non accentati nell'ordinamento.  
  
## <a name="digraph-characters"></a>Caratteri di digramma  
 In alcune lingue sono presenti caratteri alfabetici che rappresentano due caratteri distinti. Ad esempio, diversi linguaggi utilizzano il carattere `æ` per rappresentare i caratteri `a` e `e` quando vengono visualizzati insieme. L'operatore `Like` riconosce che il singolo carattere di digramma e i due caratteri singoli sono equivalenti.  
  
 Quando nelle impostazioni locali del sistema viene specificata una lingua che usa un carattere digraph, un'occorrenza del carattere singolo digramma in `pattern` o `string` corrisponde alla sequenza di due caratteri equivalente nell'altra stringa. Analogamente, un carattere di digrafo in `pattern` racchiuso tra parentesi quadre (di per sé, in un elenco o in un intervallo) corrisponde alla sequenza di due caratteri equivalente in `string`.  
  
## <a name="overloading"></a>Overload  
 L'operatore `Like` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio usa l'operatore `Like` per confrontare le stringhe con i vari modelli. I risultati vengono inseriti in una variabile @no__t 0 che indica se ogni stringa soddisfa il modello.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Procedura: Trovare la corrispondenza di una stringa con un modello @ no__t-0
