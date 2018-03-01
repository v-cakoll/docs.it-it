---
title: Istruzione Call (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a>Istruzione Call (Visual Basic)
Trasferisce il controllo a un `Function`, `Sub`, o una routine di libreria a collegamento dinamico (DLL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Parti  
 `procedureName`  
 Obbligatorio. Nome della routine da chiamare.  
  
 `argumentList`  
 Parametro facoltativo. Elenco di variabili o espressioni che rappresentano gli argomenti passati alla procedura quando viene chiamato. Più argomenti sono separati da virgole. Se si includono `argumentList`, è necessario racchiuderlo tra parentesi.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare il `Call` parola chiave quando si chiama una routine. Per la maggior parte delle chiamate di procedura, non è necessario utilizzare questa parola chiave.  
  
 In genere si usa il `Call` (parola chiave) quando l'espressione di chiamata non inizia con un identificatore. Utilizzare il `Call` (parola chiave) per altri utilizzi non è consigliato.  
  
 Se la routine restituisce un valore, il `Call` istruzione lo ignora.  
  
## <a name="example"></a>Esempio  
 Il codice riportato di seguito sono illustrati due esempi in cui il `Call` parola chiave è necessaria chiamare una routine. In entrambi gli esempi, l'espressione di chiamata non inizia con un identificatore.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
