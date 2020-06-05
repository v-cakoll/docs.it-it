---
title: Sottoespressione
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: f862730220d0595faecaa915b1eaad2a3cdc0053
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406315"
---
# <a name="sub-expression-visual-basic"></a>Sottoespressione (Visual Basic)
Dichiara i parametri e il codice che definiscono un'espressione lambda subroutine.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`parameterlist`|Facoltativa. Elenco di nomi di variabili locali che rappresentano i parametri della stored procedure. Le parentesi devono essere presenti anche quando l'elenco è vuoto. Per altre informazioni, vedere [Parameter List](../statements/parameter-list.md).|  
|`statement`|Obbligatorio. Una singola istruzione.|  
|`statements`|Obbligatorio. Elenco di istruzioni.|  
  
## <a name="remarks"></a>Commenti  
 Un' *espressione lambda* è una subroutine che non ha un nome e che esegue una o più istruzioni. È possibile usare un'espressione lambda ovunque sia possibile usare un tipo delegato, ad eccezione di un argomento di `RemoveHandler` . Per altre informazioni sui delegati e sull'uso di espressioni lambda con i delegati, vedere [istruzione Delegate](../statements/delegate-statement.md) e conversione di delegati [rilassati](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quella di una subroutine standard. Le differenze sono le seguenti:  
  
- Un'espressione lambda non ha un nome.  
  
- Un'espressione lambda non può avere un modificatore, ad esempio `Overloads` o `Overrides` .  
  
- Il corpo di un'espressione lambda a riga singola deve essere un'istruzione, non un'espressione. Il corpo può essere costituito da una chiamata a una routine Sub, ma non da una chiamata a una routine di funzione.  
  
- In un'espressione lambda, tutti i parametri devono avere tipi di dati specificati oppure è necessario dedurre tutti i parametri.  
  
- I parametri e facoltativi `ParamArray` non sono consentiti nelle espressioni lambda.  
  
- I parametri generici non sono consentiti nelle espressioni lambda.  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio di espressione lambda che scrive un valore nella console. Nell'esempio viene illustrata la sintassi delle espressioni lambda su una sola riga e su più righe per una subroutine. Per altri esempi, vedere [espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Sub](../statements/sub-statement.md)
- [Espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
- [Conversione di tipo relaxed del delegato](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
