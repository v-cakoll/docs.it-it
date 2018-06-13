---
title: Operatori di confronto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 4e37f55b4c873c3dbea22a8edf0e5e2b58824720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604926"
---
# <a name="comparison-operators-visual-basic"></a>Operatori di confronto (Visual Basic)
Di seguito sono indicati gli operatori di confronto definiti in Visual Basic.  
  
 `<` (operatore)  
  
 `<=` (operatore)  
  
 `>` (operatore)  
  
 `>=` (operatore)  
  
 `=` (operatore)  
  
 `<>` (operatore)  
  
 [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Operatore Like](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Questi operatori confrontano due espressioni per determinare se sono uguali, e in caso contrario, le differenze. `Is`, `IsNot`, e `Like` vengono discussi in dettaglio nelle pagine della Guida separate. Gli operatori di confronto relazionali sono descritti in dettaglio in questa pagina.  
  
## <a name="syntax"></a>Sintassi  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Oggetto `Boolean` valore che rappresenta il risultato del confronto.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione.  
  
 `comparisonoperator`  
 Obbligatorio. Operatore di confronto relazionale.  
  
 `object1`, `object2`  
 Obbligatorio. I nomi di oggetto di riferimento.  
  
 `string`  
 Obbligatorio. Qualsiasi espressione `String`.  
  
 `pattern`  
 Obbligatorio. Qualsiasi `String` intervallo di caratteri o espressione.  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente contiene un elenco di operatori di confronto relazionali e le condizioni che determinano se `result` è `True` o `False`.  
  
|Operatore|`True` Se|`False` Se|  
|--------------|---------------|----------------|  
|`<` (Minore di)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (Minore o uguale a)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (Maggiore di)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (Maggiore o uguale a)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (È uguale a)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (Non uguale a)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  Il [= operatore](../../../visual-basic/language-reference/operators/assignment-operator.md) viene usato anche come un operatore di assegnazione.  
  
 Il `Is` (operatore), il `IsNot` (operatore) e `Like` operatore avere le funzionalità di confronto specifiche che si differenziano dagli operatori nella tabella precedente.  
  
## <a name="comparing-numbers"></a>Il confronto tra valori  
 Quando si confronta un'espressione di tipo `Single` a uno di tipo `Double`, `Single` espressione viene convertita in `Double`. Questo comportamento è opposto a quello trovato in Visual Basic 6.  
  
 Analogamente, quando si confronta un'espressione di tipo `Decimal` a un'espressione di tipo `Single` o `Double`, `Decimal` espressione viene convertita in `Single` o `Double`. Per `Decimal` espressioni, qualsiasi valore frazionario minore 1E-28 potrebbe andare perse. Tale perdita valore frazionario potrebbe risultano uguali quando non sono di due valori. Per questo motivo, è necessario prestare attenzione quando si usa l'uguaglianza (`=`) per confrontare due variabili a virgola mobile. È più sicuro verificare se il valore assoluto della differenza tra due numeri è minore di tolleranza minima accettabile.  
  
### <a name="floating-point-imprecision"></a>A virgola mobile imprecisione  
 Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre contengono una precisa rappresentazione in memoria. Ciò potrebbe provocare risultati imprevisti da alcune operazioni, ad esempio il confronto di valori e [operatore Mod](../../../visual-basic/language-reference/operators/mod-operator.md). Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Quando si confrontano stringhe, le espressioni stringa vengono valutate in base all'ordine alfabetico, che dipende il `Option Compare` impostazione.  
  
 `Option Compare Binary` Consente i confronti per un tipo di ordinamento derivato dalle rappresentazioni binarie interne dei caratteri di stringhe. Il tipo di ordinamento è determinato dalla tabella codici. Nell'esempio seguente viene illustrato un tipico ordinamento binario.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` basi stringa i confronti per un criterio di ordinamento testuale, tra maiuscole e minuscole determinato dalle impostazioni locali dell'applicazione. Quando si imposta `Option Compare Text` e ordinare i caratteri nell'esempio precedente, si applica l'ordinamento di testo seguente:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Dipendono dalle impostazioni locali  
 Quando si imposta `Option Compare Text`, il risultato di un confronto tra stringhe può dipendere dalle impostazioni locali in cui è in esecuzione l'applicazione. Come uguali in una lingua ma non in un'altra potrebbero confrontare i due caratteri. Se si utilizza un confronto tra stringhe per decisioni importanti, ad esempio, se si desidera accettare un tentativo di accesso, dovrebbe essere tra maiuscole e minuscole delle impostazioni locali dell'avviso. Prendere in considerazione delle impostazioni `Option Compare Binary` o la chiamata di <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, che tiene conto delle impostazioni locali.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>La programmazione con gli operatori di confronto relazionale  
 L'utilizzo degli operatori di confronto relazionali con `Object` espressioni non è consentita in `Option Strict On`. Quando `Option Strict` è `Off`e `expression1` o `expression2` è un `Object` espressione, i tipi di runtime determinano la modalità di confronto. Nella tabella seguente viene illustrato come le espressioni vengono confrontate e il risultato del confronto, a seconda del tipo di runtime degli operandi.  
  
|Se gli operandi sono|Risultato del confronto è|  
|---------------------|-------------------|  
|Entrambi `String`|Confronto in base alle caratteristiche di ordinamento delle stringhe di ordinamento.|  
|Entrambi numerici|Gli oggetti convertiti in `Double`, confronto numerico.|  
|Uno numerico e uno `String`|Il `String` viene convertito in un `Double` e viene eseguito un confronto numerico. Se il `String` non può essere convertito in `Double`, un <xref:System.InvalidCastException> viene generata un'eccezione.|  
|Uno o entrambi sono tipi di riferimento diverso da `String`|Viene generato un tipo <xref:System.InvalidCastException>.|  
  
 Considerano i confronti numerici `Nothing` come 0. Confronti di stringhe considerano `Nothing` come `""` (una stringa vuota).  
  
## <a name="overloading"></a>Overload  
 Gli operatori di confronto relazionale (`<`. `<=``>`, `>=`, `=`, `<>`) può essere *overload*, ovvero una classe o struttura possibile ridefinirne il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice utilizza uno di questi operatori in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Si noti che il [= operatore](../../../visual-basic/language-reference/operators/assignment-operator.md) può essere sottoposto a overload solo come operatore di confronto relazionale, non come un operatore di assegnazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente mostra vari usi di operatori di confronto relazionali che consentono di confrontare le espressioni. Gli operatori di confronto relazionali restituiscono un `Boolean` risultato che indica se l'espressione specificata è `True`. Quando si applica il `>` e `<` agli operatori di stringhe, il confronto viene eseguito utilizzando il normale criterio di ordinamento alfabetico delle stringhe. In questo ordine può essere dipende dalle impostazioni locali. Se l'ordinamento è distinzione maiuscole/minuscole dipende il [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) impostazione.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 Nell'esempio precedente, il primo confronto restituisce `False` e gli altri confronti restituiscono `True`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.InvalidCastException>  
 [Operatore =](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
