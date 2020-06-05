---
title: Istruzione RemoveHandler
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 3514a79f2430b148e6a3727b83029b4e207a677b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404252"
---
# <a name="removehandler-statement"></a>Istruzione RemoveHandler
Rimuove l'associazione tra un evento e un gestore eventi.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`event`|Nome dell'evento da gestire.|  
|`eventhandler`|Nome della stored procedure che gestisce attualmente l'evento.|  
  
## <a name="remarks"></a>Commenti  
 Le `AddHandler` `RemoveHandler` istruzioni e consentono di avviare e arrestare la gestione degli eventi per un evento specifico in qualsiasi momento durante l'esecuzione del programma.  
  
> [!NOTE]
> Per gli eventi personalizzati, l' `RemoveHandler` istruzione richiama la funzione di `RemoveHandler` accesso dell'evento. Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione AddHandler](addhandler-statement.md)
- [Selettori](handles-clause.md)
- [Istruzione Event](event-statement.md)
- [Events](../../programming-guide/language-features/events/index.md)
