---
title: Espressione di funzione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: cfdd17f6f4ee6c4ddb3fa73ab3ec9c5ce46a162f
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137694"
---
# <a name="function-expression-visual-basic"></a>Espressione di funzione (Visual Basic)
Dichiara i parametri e il codice che definiscono un'espressione lambda function.  
  
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
|`parameterlist`|Facoltativo. Elenco di nomi delle variabili locali che rappresentano i parametri di questa procedura. Le parentesi devono essere presenti anche quando l'elenco è vuoto. Visualizzare [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Obbligatorio. Una singola espressione. Il tipo dell'espressione è il tipo restituito della funzione.|  
|`statements`|Obbligatorio. Un elenco di istruzioni che restituisce un valore utilizzando il `Return` istruzione. (Vedere [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).) Il tipo del valore restituito è il tipo restituito della funzione.|  
  
## <a name="remarks"></a>Note  
 Oggetto *espressione lambda* è una funzione senza nome, che calcola e restituisce un valore. È possibile usare un'espressione lambda in un punto qualsiasi tranne è possibile usare un tipo delegato, come argomento a `RemoveHandler`. Per altre informazioni sui delegati e l'uso delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quello di una funzione standard. Le differenze sono i seguenti:  
  
-   Un'espressione lambda non ha un nome.  
  
-   Le espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.  
  
-   Le espressioni lambda non utilizzano un `As` clausola per designare il tipo restituito della funzione. Al contrario, il tipo viene dedotto dal valore che restituisce il corpo di un'espressione lambda a riga singola, o il valore restituito di un'espressione lambda su più righe. Ad esempio, se il corpo di un'espressione lambda a riga singola `Where cust.City = "London"`, il tipo restituito è `Boolean`.  
  
-   Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non un'istruzione. Il corpo può essere costituito da una chiamata a una routine di funzione, ma non una chiamata a una routine sub.  
  
-   Tutti i parametri devono avere specificati tipi di dati o tutti devono essere dedotti.  
  
-   I parametri Paramarray e Optional non sono consentiti.  
  
-   I parametri generici non sono consentiti.  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti illustrano due modi per creare le espressioni lambda semplice. Il primo Usa un `Dim` per fornire un nome per la funzione. Per chiamare la funzione, si invia un valore per il parametro.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Esempio  
 In alternativa, è possibile dichiarare ed eseguire la funzione nello stesso momento.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Esempio  
 Ecco un esempio di un'espressione lambda che incrementa il relativo argomento e restituisce il valore. L'esempio illustra sia la sintassi delle espressioni lambda a riga singola e a più righe per una funzione. Per altri esempi, vedere [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Esempio  
 Le espressioni lambda sono alla base di molti degli operatori di query in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]e può essere usato in modo esplicito nella query basate su metodo. Nell'esempio seguente viene illustrato un tipico [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, seguita dalla conversione della query nel formato del metodo.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Per altre informazioni sui metodi di query, vedere [query](../../../visual-basic/language-reference/queries/index.md). Per altre informazioni sugli operatori di query standard, vedere [panoramica degli operatori Query Standard](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Confronto di valori](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)  
 [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
