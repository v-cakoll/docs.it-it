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
ms.openlocfilehash: a816b1097c0a9628bb2889d39be5c029beaa3c63
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200988"
---
# <a name="comparison-operators-visual-basic"></a>Operatori di confronto (Visual Basic)
Di seguito è elencati gli operatori di confronto definiti in Visual Basic.  
  
 `<` Operatore  
  
 `<=` Operatore  
  
 `>` Operatore  
  
 `>=` Operatore  
  
 `=` Operatore  
  
 `<>` Operatore  
  
 [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Operatore Like](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Questi operatori confrontano due espressioni per determinare se sono uguali, e in caso contrario, le differenze. `Is`, `IsNot`, e `Like` vengono descritti in dettaglio nelle pagine della Guida separate. Gli operatori di confronto relazionale vengono descritti in dettaglio in questa pagina.  
  
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
 Obbligatorio. Qualsiasi operatore di confronto relazionale.  
  
 `object1`, `object2`  
 Obbligatorio. Tutti i nomi degli oggetti di riferimento.  
  
 `string`  
 Obbligatorio. Qualsiasi espressione `String` .  
  
 `pattern`  
 Obbligatorio. Qualsiasi `String` espressione o un intervallo di caratteri.  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente contiene un elenco di operatori di confronto relazionale e le condizioni che determinano se `result` viene `True` o `False`.  
  
|Operatore|`True` se|`False` se|  
|--------------|---------------|----------------|  
|`<` (Minore di)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (Minore o uguale a)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (Maggiore di)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (Maggiore o uguale a)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (Uguale a)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (Non uguale a)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  Il [= (operatore)](../../../visual-basic/language-reference/operators/assignment-operator.md) viene usato anche come operatore di assegnazione.  
  
 Il `Is` operatore, la `IsNot` operatore e il `Like` operatore hanno le funzionalità di confronto specifiche che si differenziano dagli operatori nella tabella precedente.  
  
## <a name="comparing-numbers"></a>Confronto tra valori  
 Quando si confronta un'espressione di tipo `Single` a uno di tipo `Double`, il `Single` espressione viene convertita in `Double`. Questo comportamento è opposto a quello trovato in Visual Basic 6.  
  
 Analogamente, quando si confronta un'espressione di tipo `Decimal` a un'espressione di tipo `Single` oppure `Double`, il `Decimal` espressione viene convertita in `Single` o `Double`. Per `Decimal` espressioni, qualsiasi valore minore di 1E-28 frazionari potrebbe andare perse. Potrebbero essere due valori vengono considerati uguali quando non sono di perdere i dati valore frazionario. Per questo motivo, è necessario prestare attenzione quando si usa l'uguaglianza (`=`) per confrontare due variabili a virgola mobile. È più sicuro verificare se il valore assoluto della differenza tra due numeri è minore di tolleranza minima accettabile.  
  
### <a name="floating-point-imprecision"></a>A virgola mobile dell'imprecisione  
 Quando si lavora con numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione esatta in memoria. Ciò potrebbe provocare risultati imprevisti da determinate operazioni, ad esempio il confronto dei valori e le [operatore Mod](../../../visual-basic/language-reference/operators/mod-operator.md). Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Quando si confrontano stringhe, le espressioni stringa vengono valutate in base all'ordine alfabetico, che dipende la `Option Compare` impostazione.  
  
 `Option Compare Binary` Consente i confronti in un tipo di ordinamento derivato dalle rappresentazioni binarie interne dei caratteri di stringhe. L'ordinamento è determinato dalla tabella codici. L'esempio seguente illustra un tipico ordinamento binario.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` Consente di eseguire stringhe confronti su un criterio di ordinamento testuale, tra maiuscole e minuscole determinato dalle impostazioni locali dell'applicazione. Quando si imposta `Option Compare Text` e ordinano i caratteri nell'esempio precedente, si applica l'ordinamento di testo seguente:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Dipendono dalle impostazioni locali  
 Quando si imposta `Option Compare Text`, il risultato di un confronto tra stringhe può dipendere dalle impostazioni locali in cui viene eseguita l'applicazione. Due caratteri potrebbe essere considerati uguali nelle impostazioni locali, ma non in un altro. Se si usa un confronto tra stringhe per prendere decisioni importanti, ad esempio se si desidera accettare un tentativo di accesso, dovrebbe essere tra maiuscole e minuscole delle impostazioni locali dell'avviso. Prendere in considerazione delle impostazioni `Option Compare Binary` o la chiamata di <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, che tiene conto delle impostazioni locali.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>La programmazione con gli operatori di confronto relazionale  
 L'utilizzo degli operatori di confronto relazionale con `Object` espressioni non è consentita negli `Option Strict On`. Quando `Option Strict` viene `Off`e il valore `expression1` oppure `expression2` è un `Object` espressione, i tipi in fase di esecuzione determinano la modalità di confronto. Nella tabella seguente viene illustrato come vengono confrontate le espressioni e il risultato del confronto, a seconda del tipo di runtime degli operandi.  
  
|Se gli operandi sono|Risultato del confronto è|  
|---------------------|-------------------|  
|Entrambi `String`|Confronto in base alle caratteristiche di ordinamento delle stringhe di ordinamento.|  
|Entrambe numeriche|Gli oggetti convertiti in `Double`, confronto numerico.|  
|Uno numerico e uno `String`|Il `String` viene convertito in un `Double` e viene eseguito un confronto numerico. Se il `String` non può essere convertito `Double`, un <xref:System.InvalidCastException> viene generata un'eccezione.|  
|Uno o entrambi sono tipi riferimento diverso da `String`|Viene generato un tipo <xref:System.InvalidCastException>.|  
  
 Considerano i confronti numerici `Nothing` come 0. Confronti di stringhe considerano `Nothing` come `""` (una stringa vuota).  
  
## <a name="overloading"></a>Overload  
 Gli operatori di confronto relazionale (`<`. `<=``>`, `>=`, `=`, `<>`) può essere *sottoposti a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice usa uno di questi operatori in una classe o una struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Si noti che il [= (operatore)](../../../visual-basic/language-reference/operators/assignment-operator.md) può essere sottoposto a overload solo come un operatore di confronto relazionale e non come un operatore di assegnazione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra vari usi di operatori di confronto relazionale, che consente di confrontare espressioni. Gli operatori di confronto relazionale restituiscono un `Boolean` risultato che indica se l'espressione specificata è `True`. Quando si applica il `>` e `<` agli operatori di stringhe, il confronto viene eseguito utilizzando il normale di ordinamento alfabetico delle stringhe. Quest'ordine può dipendere dalle impostazioni locali. Se l'ordinamento è distinzione maiuscole/minuscole o meno dipende il [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) impostazione.  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 Nell'esempio precedente, restituisce il primo confronto `False` e gli altri confronti restituiscono `True`.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.InvalidCastException>
- [Operatore =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
