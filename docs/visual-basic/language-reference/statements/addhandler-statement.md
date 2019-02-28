---
title: Istruzione AddHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: dd57f63b5741822de7b11c1fafe90452a767aa34
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965644"
---
# <a name="addhandler-statement"></a>Istruzione AddHandler
Associa un evento a un gestore eventi in fase di esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Parti  
|||
|---|---|
|event|Il nome dell'evento da gestire.|  
|`eventhandler`|Il nome di una routine che gestisce l'evento.|
|||
  
## <a name="remarks"></a>Note  
 Il `AddHandler` e `RemoveHandler` istruzioni consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.  
  
 La firma del `eventhandler` routine deve corrispondere alla firma dell'evento `event`.  
  
 La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze. L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione. Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento. Per altre informazioni, vedere [gestisce](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Per gli eventi personalizzati, il `AddHandler` istruzione richiama l'evento `AddHandler` della funzione di accesso. Per altre informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
