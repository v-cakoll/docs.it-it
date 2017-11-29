---
title: Like (operatore) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad5729515362bfd52b0c3b401f218a49f569726e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="like-operator-visual-basic"></a>Like (operatore) (Visual Basic)
Confronta una stringa con un modello.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` variabile. Il risultato è un `Boolean` valore che indica se il `string` soddisfa il `pattern`.  
  
 `string`  
 Obbligatorio. Qualsiasi espressione `String`.  
  
 `pattern`  
 Obbligatorio. Qualsiasi `String` espressione conforme alle convenzioni di criteri di ricerca descritte in "Osservazioni".  
  
## <a name="remarks"></a>Note  
 Se il valore in `string` soddisfa il `pattern`, `result` è `True`. Se la stringa non soddisfa il criterio, `result` è `False`. Se entrambi `string` e `pattern` sono stringhe vuote, il risultato è `True`.  
  
## <a name="comparison-method"></a>Metodo di confronto  
 Il comportamento del `Like` operatore dipende il [istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md). Il metodo di confronto di stringa predefinito per ogni file di origine è `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Opzioni del modello  
 Criteri di ricerca incorporati offre uno strumento versatile per confronti tra stringhe. Le funzionalità di criteri di ricerca consentono di associare ogni carattere `string` da un carattere specifico, un carattere jolly, un elenco di caratteri o un intervallo di caratteri. La tabella seguente mostra i caratteri consentiti in `pattern` e le relative corrispondenze.  
  
|Caratteri`pattern`|Corrispondenze in`string`|  
|-----------------------------|-------------------------|  
|`?`|Qualsiasi carattere singolo|  
|`*`|Zero o più caratteri|  
|`#`|Qualsiasi cifra (0-9)|  
|`[charlist]`|Qualsiasi carattere singolo`charlist`|  
|`[!charlist]`|Qualsiasi carattere singolo non incluso`charlist`|  
  
## <a name="character-lists"></a>Elenchi di caratteri  
 Un gruppo di uno o più caratteri (`charlist`) racchiusi tra parentesi quadre (`[ ]`) può essere usato per corrispondi a qualsiasi carattere singolo in `string` e possono includere qualsiasi codice di carattere, comprese le cifre.  
  
 Un punto esclamativo (`!`) all'inizio di `charlist` indica che viene individuata una corrispondenza se qualsiasi carattere tranne i caratteri in `charlist` è presente in `string`. Se utilizzato all'esterno delle parentesi quadre, il punto esclamativo corrisponde a se stesso.  
  
## <a name="special-characters"></a>Caratteri speciali  
 Per trovare la corrispondenza di parentesi quadra sinistra i caratteri speciali (`[`), punto interrogativo (`?`), simbolo di cancelletto (`#`) e l'asterisco (`*`), racchiuderli tra parentesi quadre. La parentesi quadra chiusa (`]`) non può essere utilizzato all'interno di un gruppo per stabilire una corrispondenza, ma può essere utilizzato all'esterno di un gruppo come un singolo carattere.  
  
 La sequenza di caratteri `[]` viene considerata una stringa di lunghezza zero (`""`). Tuttavia, non può far parte di un elenco di caratteri racchiusi tra parentesi quadre. Se si desidera controllare se una posizione in `string` contiene uno di un gruppo di caratteri o nessun carattere, è possibile utilizzare `Like` due volte. Per un esempio, vedere [procedura: confrontare una stringa con un modello](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Intervalli di caratteri  
 Utilizzando un trattino (`–`) per separare i limiti inferiore e superiore dell'intervallo, `charlist` possibile specificare un intervallo di caratteri. Ad esempio, `[A–Z]` produce una corrispondenza, se la posizione corrispondente `string` contenente qualsiasi carattere all'interno dell'intervallo `A`–`Z`, e `[!H–L]` produce una corrispondenza, se la posizione corrispondente contenente qualsiasi carattere non compreso nell'intervallo `H`–`L`.  
  
 Quando si specifica un intervallo di caratteri, è necessario specificarle nell'ordine crescente, vale a dire, dalla più bassa. Di conseguenza, `[A–Z]` è valido, ma `[Z–A]` non.  
  
### <a name="multiple-character-ranges"></a>Più intervalli di caratteri  
 Per specificare più intervalli per la stessa posizione di carattere, inserirli all'interno delle parentesi stesso senza delimitatori. Ad esempio, `[A–CX–Z]` produce una corrispondenza, se la posizione corrispondente `string` contenente qualsiasi carattere compreso nell'intervallo `A`–`C` o l'intervallo `X`–`Z`.  
  
### <a name="usage-of-the-hyphen"></a>Utilizzo del trattino  
 Un segno meno (`–`) possono essere visualizzati all'inizio (dopo un punto esclamativo, se presente) o alla fine di `charlist` per stabilire una corrispondenza. In qualsiasi altro percorso, il trattino identifica un intervallo di caratteri racchiusi tra i caratteri su entrambi i lati del trattino.  
  
## <a name="collating-sequence"></a>Sequenza di confronto  
 Il significato di un intervallo specificato dipende dall'ordinamento dei caratteri in fase di esecuzione, come determinato dalla `Option``Compare` e le impostazioni locali del sistema in cui viene eseguito il codice. Con `Option``Compare``Binary`, l'intervallo `[A–E]` corrisponde `A`, `B`, `C`, `D`, e `E`. Con `Option``Compare``Text`, `[A–E]` corrisponde `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, e `e`. L'intervallo corrisponde `Ê` o `ê` perché i caratteri accentati collate dopo accentati nell'ordinamento.  
  
## <a name="digraph-characters"></a>Caratteri digraph  
 In alcune lingue, sono presenti caratteri alfabetici che rappresentano due caratteri distinti. Ad esempio, di utilizzare il carattere più lingue `æ` per rappresentare i caratteri `a` e `e` quando vengono visualizzati insieme. Il `Like` operatore riconosce che il singolo carattere digraph e i due caratteri singoli sono equivalenti.  
  
 Quando una lingua che utilizza un carattere digraph è specificata nelle impostazioni locali del sistema, di un'occorrenza del carattere in una tale `pattern` o `string` corrisponde alla sequenza di due caratteri equivalente in altra stringa. Analogamente, un carattere digraph in `pattern` racchiusi tra parentesi quadre (di per sé, in un elenco o in un intervallo) corrisponde alla sequenza di due caratteri equivalente in `string`.  
  
## <a name="overloading"></a>Overload  
 Il `Like` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Like` operatore per confrontare le stringhe in vari modelli. I risultati vengono inseriti in un `Boolean` variabile che indica se ogni stringa soddisfa il criterio.  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Procedura: Confrontare una stringa con un modello](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
