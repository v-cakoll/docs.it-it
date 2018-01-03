---
title: Evento ETW di eccezione generata_V1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 60013d0df8c63033f6da8d61479bacac7b944094
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="exception-thrownv1-etw-event"></a>Evento ETW di eccezione generata_V1
Questo evento acquisisce informazioni sulle eccezioni generate.  
  
 La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso. Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Livello|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Avviso (2)|  
  
 La tabella seguente offre informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Viene generata un'eccezione gestita.|  
  
 La tabella seguente mostra i dati degli eventi.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|Tipo di eccezione|win:UnicodeString|Tipo dell'eccezione, ad esempio `System.NullReferenceException`.|  
|Messaggio dell'eccezione|win:UnicodeString|Messaggio effettivo dell'eccezione.|  
|EIPCodeThrow|win:Pointer|Puntatore dell'istruzione in cui si è verificata l'eccezione.|  
|ExceptionHR|win:UInt32|[HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679) dell'eccezione.|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException. Vedere [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) (Eventi ETW di CLR) nella documentazione di Visual Basic.<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException. Indica che lo stato del processo è danneggiato. Vedere [Gestione delle eccezioni di stato danneggiato](http://go.microsoft.com/fwlink/?LinkId=179681) su MSDN.<br /><br /> 0x10: IsCLSCompliant. Un'eccezione derivante da <xref:System.Exception> è conforme a CLS. In caso contrario, non è conforme a CLS.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md)
