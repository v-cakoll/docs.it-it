---
title: Sottoespressione (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 43e35bd0386bc56478603ec36437981785cc8ffb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sub-expression-visual-basic"></a>Sottoespressione (Visual Basic)
Dichiara i parametri e il codice che definiscono un'espressione lambda subroutine.  
  
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
|`parameterlist`|Parametro facoltativo. Un elenco di nomi di variabili locali che rappresentano i parametri della procedura. Le parentesi devono essere presenti anche quando l'elenco è vuoto. Per ulteriori informazioni, vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Obbligatorio. Una singola istruzione.|  
|`statements`|Obbligatorio. Un elenco di istruzioni.|  
  
## <a name="remarks"></a>Note  
 Oggetto *espressione lambda* è una subroutine che non dispone di un nome e che viene eseguita una o più istruzioni. È possibile usare qualsiasi un'espressione lambda che è possibile utilizzare un tipo delegato, tranne come argomento di `RemoveHandler`. Per ulteriori informazioni sui delegati e l'utilizzo delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quello di una subroutine standard. Come indicato di seguito sono riportate le differenze:  
  
-   Un'espressione lambda non ha un nome.  
  
-   Un'espressione lambda non può avere un modificatore, ad esempio `Overloads` o `Overrides`.  
  
-   Il corpo di un'espressione lambda a riga singola deve essere un'istruzione, non è un'espressione. Il corpo può essere costituito da una chiamata a una routine sub, ma non una chiamata a una routine di funzione.  
  
-   In un'espressione lambda, tutti i parametri devono avere specificati tipi di dati o tutti i parametri devono essere dedotti.  
  
-   Parametro facoltativo e `ParamArray` parametri non sono consentiti nelle espressioni lambda.  
  
-   Parametri generici non sono consentiti nelle espressioni lambda.  
  
## <a name="example"></a>Esempio  
 Ecco un esempio di un'espressione lambda che scrive un valore nella console. L'esempio illustra entrambi la sintassi di espressione lambda a riga singola e su più righe di una subroutine. Per ulteriori esempi, vedere [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
