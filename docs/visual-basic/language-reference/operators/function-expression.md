---
title: Espressione di funzione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 29bf95a336b6f6ed5c9c310c9ea7575a91089361
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604887"
---
# <a name="function-expression-visual-basic"></a>Espressione di funzione (Visual Basic)
Dichiara i parametri e il codice che definiscono un'espressione lambda di funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`parameterlist`|Facoltativo. Un elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Le parentesi devono essere presenti anche quando l'elenco è vuoto. Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Obbligatorio. Una singola espressione. Il tipo dell'espressione è il tipo restituito della funzione.|  
|`statements`|Obbligatorio. Un elenco di istruzioni che restituisce un valore utilizzando il `Return` istruzione. (Vedere [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).) Il tipo del valore restituito è il tipo restituito della funzione.|  
  
## <a name="remarks"></a>Note  
 Oggetto *espressione lambda* è una funzione senza nome, che calcola e restituisce un valore. È possibile utilizzare un'espressione lambda in qualsiasi punto è possibile utilizzare un tipo delegato, ad eccezione di come un argomento a `RemoveHandler`. Per ulteriori informazioni sui delegati e l'utilizzo delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quello di una funzione standard. Come indicato di seguito sono riportate le differenze:  
  
-   Un'espressione lambda non ha un nome.  
  
-   Espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.  
  
-   Le espressioni lambda non utilizzano un `As` clausola per definire il tipo restituito della funzione. Al contrario, il tipo viene dedotto dal valore che restituisce il corpo di un'espressione lambda a riga singola o il valore restituito di un'espressione lambda su più righe. Ad esempio, se il corpo di un'espressione lambda a riga singola `Where cust.City = "London"`, il tipo restituito è `Boolean`.  
  
-   Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non è un'istruzione. Il corpo può essere costituito da una chiamata a una routine function, ma non una chiamata a una routine sub.  
  
-   Tutti i parametri devono avere specificati devono dedurre i tipi di dati o tutti.  
  
-   Parametri facoltativi e Paramarray non sono consentiti.  
  
-   Parametri generici non sono consentiti.  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti mostrano due modi per creare espressioni lambda semplici. Il primo Usa un `Dim` per fornire un nome per la funzione. Per chiamare la funzione, si invia un valore per il parametro.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Esempio  
 In alternativa, è possibile dichiarare ed eseguire la funzione allo stesso tempo.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Esempio  
 Ecco un esempio di un'espressione lambda che incrementa il relativo argomento e restituisce il valore. L'esempio mostra sia la sintassi di espressione lambda a riga singola e su più righe per una funzione. Per ulteriori esempi, vedere [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Esempio  
 Espressioni lambda sottostanti molti degli operatori di query in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]e può essere utilizzato in modo esplicito nella query basate su metodo. Nell'esempio seguente viene illustrato un tipico [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, seguita dalla conversione della query in formato del metodo.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Per ulteriori informazioni sui metodi di query, vedere [query](../../../visual-basic/language-reference/queries/queries.md). Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di Query Standard](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Confronto di valori](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)  
 [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
