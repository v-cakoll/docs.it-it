---
title: Sottoespressione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5b26a091dc8eb7415702c3c2853a569324def7d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824611"
---
# <a name="sub-expression-visual-basic"></a>Sottoespressione (Visual Basic)
Dichiara i parametri e il codice che definiscono un'espressione lambda di subroutine.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`parameterlist`|Facoltativo. Elenco di nomi delle variabili locali che rappresentano i parametri della procedura. Le parentesi devono essere presenti anche quando l'elenco è vuoto. Per altre informazioni, vedere [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Obbligatorio. Una singola istruzione.|  
|`statements`|Obbligatorio. Un elenco di istruzioni.|  
  
## <a name="remarks"></a>Note  
 Oggetto *espressione lambda* è una subroutine che non dispone di un nome e che esegue una o più istruzioni. È possibile usare un'espressione lambda in qualsiasi punto che è possibile usare un tipo delegato, ad eccezione come argomento a `RemoveHandler`. Per altre informazioni sui delegati e l'uso delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quello di una subroutine standard. Le differenze sono i seguenti:  
  
-   Un'espressione lambda non ha un nome.  
  
-   Un'espressione lambda non può avere un modificatore, ad esempio `Overloads` o `Overrides`.  
  
-   Il corpo di un'espressione lambda a riga singola deve essere un'istruzione, non un'espressione. Il corpo può essere costituito da una chiamata a una routine sub, ma non da una chiamata a una routine di funzione.  
  
-   In un'espressione lambda, tutti i parametri devono avere specificati tipi di dati o tutti i parametri devono essere dedotti.  
  
-   Facoltativo e `ParamArray` parametri non sono consentiti nelle espressioni lambda.  
  
-   I parametri generici non sono consentiti nelle espressioni lambda.  
  
## <a name="example"></a>Esempio  
 Ecco un esempio di un'espressione lambda che scrive un valore nella console. L'esempio illustra sia la sintassi delle espressioni lambda a riga singola e a più righe di una subroutine. Per altri esempi, vedere [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
- [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
