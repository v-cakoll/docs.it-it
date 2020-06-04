---
title: Istruzione AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408484"
---
# <a name="addhandler-statement"></a>Istruzione AddHandler
Associa un evento a un gestore eventi in fase di esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Parti  
|||
|---|---|
|event|Nome dell'evento da gestire.|  
|`eventhandler`|Nome di una routine che gestisce l'evento.|
|||
  
## <a name="remarks"></a>Commenti  
 Le `AddHandler` `RemoveHandler` istruzioni e consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.  
  
 La firma della `eventhandler` stored procedure deve corrispondere alla firma dell'evento `event` .  
  
 La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze. L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione. Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento. Per ulteriori informazioni, vedere [handle](handles-clause.md).  
  
> [!NOTE]
> Per gli eventi personalizzati, l' `AddHandler` istruzione richiama la funzione di `AddHandler` accesso dell'evento. Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione RemoveHandler](removehandler-statement.md)
- [Selettori](handles-clause.md)
- [Istruzione Event](event-statement.md)
- [Events](../../programming-guide/language-features/events/index.md)
