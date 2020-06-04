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
ms.openlocfilehash: 3f49f05f1deb2027b03bbf3443ca44f30c44344e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404213"
---
# <a name="resume-statement"></a>Istruzione Resume
Riprende l'esecuzione al termine di una routine di gestione degli errori.  
  
 Si consiglia di utilizzare la gestione delle eccezioni strutturata nel codice, quando possibile, anziché utilizzare la gestione delle eccezioni non strutturata e le `On Error` `Resume` istruzioni e. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Parti  
 `Resume`  
 Obbligatorio. Se l'errore si è verificato nella stessa procedura del gestore degli errori, l'esecuzione riprende con l'istruzione che ha causato l'errore. Se l'errore si è verificato in una routine chiamata, l'esecuzione riprende in corrispondenza dell'istruzione che ha eseguito l'ultima chiamata alla routine che contiene la routine di gestione degli errori.  
  
 `Next`  
 Facoltativa. Se l'errore si è verificato nella stessa procedura del gestore degli errori, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha causato l'errore. Se l'errore si è verificato in una routine chiamata, l'esecuzione riprende con l'istruzione immediatamente successiva all'istruzione che ha eseguito l'ultima chiamata alla routine che contiene la routine di gestione degli errori (o `On Error Resume Next` istruzione).  
  
 `line`  
 Facoltativa. L'esecuzione riprende in corrispondenza della riga specificata nell' `line` argomento obbligatorio. L' `line` argomento è un'etichetta di riga o un numero di riga e deve essere nella stessa procedura del gestore degli errori.  
  
## <a name="remarks"></a>Commenti  
  
> [!NOTE]
> Si consiglia di utilizzare la gestione delle eccezioni strutturata nel codice, quando possibile, anziché utilizzare la gestione delle eccezioni non strutturata e le `On Error` `Resume` istruzioni e. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](try-catch-finally-statement.md).  
  
 Se si utilizza un' `Resume` istruzione in un punto qualsiasi di una routine di gestione degli errori, si verificherà un errore.  
  
 L' `Resume` istruzione non può essere utilizzata in nessuna routine che contiene un' `Try...Catch...Finally` istruzione.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata l' `Resume` istruzione per terminare la gestione degli errori in una stored procedure e quindi riprendere l'esecuzione con l'istruzione che ha causato l'errore. Viene generato l'errore numero 55 per illustrare l'uso dell' `Resume` istruzione.  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
- [Istruzione Error](error-statement.md)
- [Istruzione On Error](on-error-statement.md)
