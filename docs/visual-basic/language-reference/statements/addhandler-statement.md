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
ms.openlocfilehash: a9913cd682e52562422ba140e27187d37c592684
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928945"
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
|event|Nome dell'evento da gestire.|  
|`eventhandler`|Nome di una routine che gestisce l'evento.|
|||
  
## <a name="remarks"></a>Note  
 Le `AddHandler` istruzioni `RemoveHandler` e consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.  
  
 La firma della `eventhandler` stored procedure deve corrispondere alla firma dell'evento `event`.  
  
 La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze. L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione. Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento. Per ulteriori informazioni, vedere [handle](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
> Per gli eventi personalizzati, `AddHandler` l'istruzione richiama la funzione di `AddHandler` accesso dell'evento. Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
