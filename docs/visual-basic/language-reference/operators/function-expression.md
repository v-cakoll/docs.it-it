---
title: Espressione di funzione
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 454c4e3d926640934a8edc4fcb16e4308a89dd50
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632337"
---
# <a name="function-expression-visual-basic"></a>Espressione di funzione (Visual Basic)
Dichiara i parametri e il codice che definiscono un'espressione lambda di funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Componenti  
  
|Termine|Definizione|  
|---|---|  
|`parameterlist`|Parametro facoltativo. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Le parentesi devono essere presenti anche quando l'elenco è vuoto. Vedere [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Richiesto. Espressione singola. Il tipo dell'espressione è il tipo restituito della funzione.|  
|`statements`|Richiesto. Elenco di istruzioni che restituiscono un valore tramite l'istruzione `Return`. (Vedere [istruzione return](../../../visual-basic/language-reference/statements/return-statement.md)). Il tipo del valore restituito è il tipo restituito della funzione.|  
  
## <a name="remarks"></a>Note  
 Un' *espressione lambda* è una funzione senza nome che calcola e restituisce un valore. È possibile usare un'espressione lambda ovunque sia possibile usare un tipo di delegato, ad eccezione di un argomento per `RemoveHandler`. Per altre informazioni sui delegati e sull'uso di espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e conversione di delegati [rilassati](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quella di una funzione standard. Le differenze sono le seguenti:  
  
- Un'espressione lambda non ha un nome.  
  
- Le espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.  
  
- Le espressioni lambda non utilizzano una clausola `As` per definire il tipo restituito della funzione. Al contrario, il tipo viene dedotto dal valore al quale il corpo di un'espressione lambda a riga singola restituisce oppure il valore restituito di un'espressione lambda su più righe. Se, ad esempio, il corpo di un'espressione lambda a riga singola è `Where cust.City = "London"`, il tipo restituito è `Boolean`.  
  
- Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non un'istruzione. Il corpo può essere costituito da una chiamata a una routine della funzione, ma non da una chiamata a una routine Sub.  
  
- È necessario dedurre tutti i parametri con i tipi di dati specificati.  
  
- I parametri facoltativi e ParamArray non sono consentiti.  
  
- I parametri generici non sono consentiti.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti vengono illustrati due modi per creare espressioni lambda semplici. Il primo usa un `Dim` per fornire un nome per la funzione. Per chiamare la funzione, si invia un valore per il parametro.  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a>Esempio  
 In alternativa, è possibile dichiarare ed eseguire la funzione nello stesso momento.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio di espressione lambda che incrementa il relativo argomento e restituisce il valore. Nell'esempio viene illustrata la sintassi delle espressioni lambda su una sola riga e su più righe per una funzione. Per altri esempi, vedere [espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a>Esempio  
 Le espressioni lambda sono sottostanti molti degli operatori di query in LINQ (Language Integrated Query) e possono essere utilizzate in modo esplicito nelle query basate su metodo. Nell'esempio seguente viene illustrata una tipica query LINQ, seguita dalla conversione della query nel formato del metodo.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Per ulteriori informazioni sui metodi di query, vedere [query](../../../visual-basic/language-reference/queries/index.md). Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di query standard](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
- [Confronto di valori](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)
- [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
