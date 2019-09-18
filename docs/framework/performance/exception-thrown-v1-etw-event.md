---
title: Evento ETW di eccezione generata_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91abd9e6f31380b7e8cd3df1a14aa5c5722901ba
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046507"
---
# <a name="exception-thrown_v1-etw-event"></a>Evento ETW di eccezione generata_V1
Questo evento acquisisce informazioni sulle eccezioni generate.  
  
 La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso. Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Avviso (2)|  
  
 La tabella seguente offre informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Viene generata un'eccezione gestita.|  
  
 La tabella seguente mostra i dati degli eventi.  
  
|Nome campo|Tipo di dati|DESCRIZIONE|  
|----------------|---------------|-----------------|  
|Tipo di eccezione|win:UnicodeString|Tipo dell'eccezione, ad esempio `System.NullReferenceException`.|  
|Messaggio dell'eccezione|win:UnicodeString|Messaggio effettivo dell'eccezione.|  
|EIPCodeThrow|win:Pointer|Puntatore dell'istruzione in cui si è verificata l'eccezione.|  
|ExceptionHR|win:UInt32|[HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679) dell'eccezione.|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (vedere [gli eventi ETW di CLR](clr-etw-events.md) nella documentazione di Visual Basic).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (indica che lo stato del processo è danneggiato; vedere [gestione delle eccezioni di stato danneggiate](https://go.microsoft.com/fwlink/?LinkId=179681) in MSDN).<br /><br /> 0x10 IsCLSCompliant (un'eccezione che deriva da <xref:System.Exception> è conforme a CLS; in caso contrario, non è conforme a CLS).|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)
