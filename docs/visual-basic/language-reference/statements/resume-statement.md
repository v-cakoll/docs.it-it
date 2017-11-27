---
title: Istruzione Resume
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb4334f302c07c81b6b8a7d0626be08cc69b1ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="resume-statement"></a>Istruzione Resume
Riprende l'esecuzione dopo il completamento di una routine di gestione degli errori.  
  
 Si consiglia di utilizzare Gestione strutturata delle eccezioni nel codice ogni volta che è possibile, anziché utilizzare la gestione delle eccezioni non strutturata e `On Error` e `Resume` istruzioni. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Parti  
 `Resume`  
 Obbligatorio. Se si è verificato l'errore nella stessa routine del gestore errori, l'esecuzione riprende con l'istruzione che ha causato l'errore. Se si è verificato l'errore in una routine chiamata, l'esecuzione riprende in corrispondenza dell'istruzione che ha richiamato la routine di gestione degli errori.  
  
 `Next`  
 Parametro facoltativo. Se si è verificato l'errore nella stessa routine del gestore errori, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore. Se si è verificato l'errore in una routine chiamata, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha richiamato la routine di gestione degli errori (o `On Error Resume Next` istruzione).  
  
 `line`  
 Parametro facoltativo. Esecuzione riprende in corrispondenza della riga specificata nell'obbligatorio `line` argomento. Il `line` argomento è un'etichetta o un numero di riga e deve trovarsi nella stessa routine del gestore errori.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  È consigliabile utilizzare Gestione strutturata delle eccezioni nel codice ogni volta che è possibile, anziché utilizzare la gestione delle eccezioni non strutturata e `On Error` e `Resume` istruzioni. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Se si utilizza un `Resume` si verifica un errore di istruzione in un contesto diverso da una routine di gestione degli errori,.  
  
 Il `Resume` istruzione non può essere utilizzata in tutte le procedure che contiene un `Try...Catch...Finally` istruzione.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Resume` istruzione per terminare una routine di gestione degli errori e quindi riprendere l'esecuzione con l'istruzione che ha causato l'errore. Numero di errore 55 viene generato per illustrare l'utilizzo del `Resume` istruzione.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>Requisiti  
 **Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** libreria di Runtime di Visual Basic (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Istruzione Error](../../../visual-basic/language-reference/statements/error-statement.md)  
 [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
