---
title: Istruzione Throw (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ada551c32b8296f0dad2ae929ca9c81a14a711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="throw-statement-visual-basic"></a>Istruzione Throw (Visual Basic)
Genera un'eccezione all'interno di una stored procedure.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Vengono fornite informazioni sull'eccezione generata. Facoltativo quando risiede in un `Catch` istruzione, è necessario in caso contrario.  
  
## <a name="remarks"></a>Note  
 Il `Throw` istruzione genera un'eccezione che è possibile gestire con un codice di gestione delle eccezioni strutturata (`Try`... `Catch`... `Finally`) o il codice di gestione delle eccezioni non strutturato (`On Error GoTo`). È possibile utilizzare il `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta verso l'alto lo stack di chiamate fino a individuare il codice di gestione delle eccezioni appropriato.  
  
 Oggetto `Throw` istruzione senza un'espressione può essere utilizzata solo un `Catch` istruzione, in cui l'istruzione case, viene rigenerata l'eccezione attualmente gestita dal `Catch` istruzione.  
  
 Il `Throw` istruzione Reimposta lo stack di chiamate per il `expression` eccezione. Se `expression` non viene specificato, lo stack di chiamate resta invariato. È possibile accedere lo stack di chiamate dell'eccezione tramite la <xref:System.Exception.StackTrace%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Il codice seguente usa il `Throw` istruzione per generare un'eccezione:  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a>Requisiti  
 **Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modulo:**`Interaction`  
  
 **Assembly:** libreria di Runtime di Visual Basic (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
