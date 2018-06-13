---
title: Istruzione Resume
ms.date: 07/20/2015
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
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603782"
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
 Facoltativo. Se si è verificato l'errore nella stessa routine del gestore errori, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore. Se si è verificato l'errore in una routine chiamata, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha richiamato la routine di gestione degli errori (o `On Error Resume Next` istruzione).  
  
 `line`  
 Facoltativo. Esecuzione riprende in corrispondenza della riga specificata nell'obbligatorio `line` argomento. Il `line` argomento è un'etichetta o un numero di riga e deve trovarsi nella stessa routine del gestore errori.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  È consigliabile utilizzare Gestione strutturata delle eccezioni nel codice ogni volta che è possibile, anziché utilizzare la gestione delle eccezioni non strutturata e `On Error` e `Resume` istruzioni. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Se si utilizza un `Resume` si verifica un errore di istruzione in un contesto diverso da una routine di gestione degli errori,.  
  
 Il `Resume` istruzione non può essere utilizzata in tutte le procedure che contiene un `Try...Catch...Finally` istruzione.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Resume` istruzione per terminare una routine di gestione degli errori e quindi riprendere l'esecuzione con l'istruzione che ha causato l'errore. Numero di errore 55 viene generato per illustrare l'utilizzo del `Resume` istruzione.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>Requisiti  
 **Namespace:** [VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** libreria di Runtime di Visual Basic (in VisualBasic)  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Istruzione Error](../../../visual-basic/language-reference/statements/error-statement.md)  
 [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
