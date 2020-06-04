---
title: Operatore Like
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
ms.openlocfilehash: 4279d90c74c80403146448a8ba5a6051ec9d12f6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401556"
---
# <a name="like-operator-visual-basic"></a>Like (operatore) (Visual Basic)
Confronta una stringa con un modello.  

> [!IMPORTANT]
> L' `Like` operatore non è attualmente supportato nei progetti .NET Core e .NET standard.

## <a name="syntax"></a>Sintassi  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` variabile. Il risultato è un `Boolean` valore che indica se l'oggetto `string` soddisfa o meno `pattern` .  
  
 `string`  
 Obbligatorio. Qualsiasi espressione `String` .  
  
 `pattern`  
 Obbligatorio. Qualsiasi `String` espressione conforme alle convenzioni dei criteri di ricerca descritte in "osservazioni".  
  
## <a name="remarks"></a>Commenti  
 Se il valore in `string` soddisfa il modello contenuto in `pattern` , `result` è `True` . Se la stringa non soddisfa il criterio, `result` è `False` . Se `string` e `pattern` sono stringhe vuote, il risultato è `True` .  
  
## <a name="comparison-method"></a>Metodo di confronto  
 Il comportamento dell' `Like` operatore dipende dall' [istruzione Option Compare](../statements/option-compare-statement.md). Il metodo di confronto tra stringhe predefinito per ogni file di origine è `Option Compare Binary` .  
  
## <a name="pattern-options"></a>Opzioni modello  
 Criteri di ricerca predefiniti fornisce uno strumento versatile per i confronti tra stringhe. Le funzionalità dei criteri di ricerca consentono di associare ogni carattere in a `string` un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri. Nella tabella seguente vengono illustrati i caratteri consentiti in e le relative `pattern` corrispondenze.  
  
|Caratteri in`pattern`|Corrisponde a`string`|  
|-----------------------------|-------------------------|  
|`?`|Un solo carattere|  
|`*`|Zero o più caratteri|  
|`#`|Qualsiasi cifra singola (0-9)|  
|`[charlist]`|Qualsiasi carattere singolo in`charlist`|  
|`[!charlist]`|Qualsiasi carattere singolo non presente in`charlist`|  
  
## <a name="character-lists"></a>Elenchi di caratteri  
 Un gruppo di uno o più caratteri ( `charlist` ) racchiusi tra parentesi quadre ( `[ ]` ) può essere usato per trovare la corrispondenza con qualsiasi carattere singolo in `string` e può includere quasi tutti i codici carattere, incluse le cifre.  
  
 Un punto esclamativo ( `!` ) all'inizio di `charlist` indica che viene effettuata una corrispondenza se viene trovato un carattere ad eccezione dei caratteri in `charlist` `string` . Quando viene usato all'esterno delle parentesi quadre, il punto esclamativo corrisponde a se stesso.  
  
## <a name="special-characters"></a>Caratteri speciali  
 Per trovare la corrispondenza tra i caratteri speciali ( `[` ), il punto interrogativo ( `?` ), il simbolo di cancelletto () `#` e l'asterisco ( `*` ), racchiuderli tra parentesi quadre. La parentesi quadra chiusa ( `]` ) non può essere usata all'interno di un gruppo per trovare la corrispondenza, ma può essere usata all'esterno di un gruppo come singolo carattere.  
  
 La sequenza di caratteri `[]` è considerata una stringa di lunghezza zero ( `""` ). Tuttavia, non può far parte di un elenco di caratteri racchiuso tra parentesi quadre. Se si desidera controllare se una posizione in `string` contiene uno di un gruppo di caratteri o nessun carattere, è possibile utilizzare `Like` due volte. Per un esempio, vedere [procedura: trovare la corrispondenza di una stringa con un modello](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Intervalli di caratteri  
 Utilizzando un trattino ( `–` ) per separare i limiti inferiore e superiore dell'intervallo, `charlist` può specificare un intervallo di caratteri. Se ad esempio `[A–Z]` la posizione del carattere corrispondente in contiene un carattere compreso nell'intervallo, viene generata una corrispondenza se la posizione del `string` `A` `Z` `[!H–L]` carattere corrispondente contiene un carattere non compreso nell'intervallo, `H` ovvero `L` .  
  
 Quando si specifica un intervallo di caratteri, questi devono essere visualizzati in ordine crescente, ovvero dal più basso al più alto. Pertanto, `[A–Z]` è un modello valido, ma `[Z–A]` non lo è.  
  
### <a name="multiple-character-ranges"></a>Più intervalli di caratteri  
 Per specificare più intervalli per la stessa posizione del carattere, inserirli all'interno delle stesse parentesi quadre senza delimitatori. Ad esempio, `[A–CX–Z]` restituisce una corrispondenza se la posizione del carattere corrispondente in `string` contiene qualsiasi carattere compreso nell'intervallo `A` `C` o nell'intervallo `X` - `Z` .  
  
### <a name="usage-of-the-hyphen"></a>Utilizzo del trattino  
 Un trattino ( `–` ) può apparire all'inizio (dopo un punto esclamativo, se presente) o alla fine di `charlist` per corrispondere a se stesso. In qualsiasi altra posizione, il segno meno identifica un intervallo di caratteri delimitati dai caratteri su entrambi i lati del segno meno.  
  
## <a name="collating-sequence"></a>Sequenza di fascicolazione  
 Il significato di un intervallo specificato dipende dall'ordinamento dei caratteri in fase di esecuzione, come determinato da `Option Compare` e dalle impostazioni locali del sistema in cui è in esecuzione il codice. Con `Option Compare Binary` , l'intervallo `[A–E]` corrisponde a,,, `A` `B` `C` `D` e `E` . Con `Option Compare Text` , `[A–E]` corrisponde a `A` , `a` ,, `À` `à` , `B` , `b` , `C` , `c` , `D` , `d` , `E` e `e` . L'intervallo non corrisponde `Ê` o `ê` perché i caratteri accentati vengono ordinati dopo caratteri non accentati nell'ordinamento.  
  
## <a name="digraph-characters"></a>Caratteri di digramma  
 In alcune lingue sono presenti caratteri alfabetici che rappresentano due caratteri distinti. Ad esempio, diversi linguaggi utilizzano il carattere `æ` per rappresentare i caratteri `a` e `e` quando vengono visualizzati insieme. L' `Like` operatore riconosce che il singolo carattere di digramma e i due caratteri singoli sono equivalenti.  
  
 Quando nelle impostazioni locali del sistema viene specificata una lingua che usa un carattere digraph, un'occorrenza del singolo carattere di digramma in `pattern` o `string` corrisponde alla sequenza di due caratteri equivalente nell'altra stringa. Analogamente, un carattere di digramma `pattern` racchiuso tra parentesi quadre (di per sé, in un elenco o in un intervallo) corrisponde alla sequenza di due caratteri equivalente in `string` .  
  
## <a name="overloading"></a>Overload  
 L' `Like` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio usa l' `Like` operatore per confrontare le stringhe con i vari modelli. I risultati entrano in una `Boolean` variabile che indica se ogni stringa soddisfa il modello.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [Operatori di confronto](comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Istruzione Option Compare](../statements/option-compare-statement.md)
- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Procedura: confrontare una stringa con un modello](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
