---
title: Espressione di funzione
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: a9b621ff03f833fcf0f07f876fd864ee963bef75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371181"
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
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`parameterlist`|Facoltativa. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Le parentesi devono essere presenti anche quando l'elenco è vuoto. Vedere [elenco di parametri](../statements/parameter-list.md).|  
|`expression`|Obbligatorio. Espressione singola. Il tipo dell'espressione è il tipo restituito della funzione.|  
|`statements`|Obbligatorio. Elenco di istruzioni che restituiscono un valore tramite l' `Return` istruzione. (Vedere [istruzione return](../statements/return-statement.md)). Il tipo del valore restituito è il tipo restituito della funzione.|  
  
## <a name="remarks"></a>Commenti  
 Un' *espressione lambda* è una funzione senza nome che calcola e restituisce un valore. È possibile usare un'espressione lambda in qualsiasi punto in cui è possibile usare un tipo delegato, ad eccezione di un argomento di `RemoveHandler` . Per altre informazioni sui delegati e sull'uso di espressioni lambda con i delegati, vedere [istruzione Delegate](../statements/delegate-statement.md) e conversione di delegati [rilassati](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quella di una funzione standard. Le differenze sono le seguenti:  
  
- Un'espressione lambda non ha un nome.  
  
- Le espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides` .  
  
- Le espressioni lambda non utilizzano una `As` clausola per definire il tipo restituito della funzione. Al contrario, il tipo viene dedotto dal valore al quale il corpo di un'espressione lambda a riga singola restituisce oppure il valore restituito di un'espressione lambda su più righe. Se, ad esempio, il corpo di un'espressione lambda a riga singola è `Where cust.City = "London"` , il tipo restituito sarà `Boolean` .  
  
- Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non un'istruzione. Il corpo può essere costituito da una chiamata a una routine della funzione, ma non da una chiamata a una routine Sub.  
  
- È necessario dedurre tutti i parametri con i tipi di dati specificati.  
  
- I parametri facoltativi e ParamArray non sono consentiti.  
  
- I parametri generici non sono consentiti.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti vengono illustrati due modi per creare espressioni lambda semplici. Il primo usa un oggetto `Dim` per fornire un nome per la funzione. Per chiamare la funzione, si invia un valore per il parametro.  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a>Esempio  
 In alternativa, è possibile dichiarare ed eseguire la funzione nello stesso momento.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio di espressione lambda che incrementa il relativo argomento e restituisce il valore. Nell'esempio viene illustrata la sintassi delle espressioni lambda su una sola riga e su più righe per una funzione. Per altri esempi, vedere [espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
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
  
 Per ulteriori informazioni sui metodi di query, vedere [query](../queries/index.md). Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di query standard](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Function](../statements/function-statement.md)
- [Espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
- [Confronto di valori](../../programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Espressioni booleane](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatore If](if-operator.md)
- [Conversione di tipo relaxed del delegato](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
