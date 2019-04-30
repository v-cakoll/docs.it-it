---
title: Istruzione Call (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945067"
---
# <a name="call-statement-visual-basic"></a>Istruzione Call (Visual Basic)
Trasferisce il controllo a un `Function`, `Sub`, o una routine di libreria di collegamento dinamico (DLL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Parti  
|||
|---|---|
|`procedureName`|Obbligatorio. Nome della routine da chiamare.|
|`argumentList`|Facoltativo. Elenco di variabili o espressioni che rappresentano gli argomenti passati alla procedura quando viene chiamato. Più argomenti sono separati da virgole. Se si includono `argumentList`, è necessario racchiuderlo tra parentesi.|
|||
  
## <a name="remarks"></a>Note  
 È possibile usare il `Call` parola chiave quando si chiama una routine. Per la maggior parte delle chiamate di routine, non è necessario utilizzare questa parola chiave.  
  
 In genere si usa il `Call` parola chiave quando l'espressione di chiamata non inizia con un identificatore. Usare il `Call` non è consigliabile la parola chiave per altri usi.  
  
 Se la routine restituisce un valore, il `Call` istruzione lo ignora.  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra due esempi in cui il `Call` parola chiave è necessario chiamare una routine. In entrambi gli esempi, l'espressione di chiamata non inizia con un identificatore.  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
