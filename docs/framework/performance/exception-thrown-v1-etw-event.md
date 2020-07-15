---
title: Evento ETW di eccezione generata_V1
description: Visualizzare informazioni dettagliate sull'evento ExceptionThrown_V1 ETW. I dati dell'evento, ad esempio i nomi dei campi, i tipi di dati e le descrizioni vengono forniti per le eccezioni generate.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f800a43d0ed2a82bc51a5e3a028b5fa1870df3fb
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309456"
---
# <a name="exception-thrown_v1-etw-event"></a>Evento ETW di eccezione generata_V1
Questo evento acquisisce informazioni sulle eccezioni generate.  
  
 La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso. Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Livello|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Avviso (2)|  
  
 La tabella seguente offre informazioni sull'evento.  
  
|Evento|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Viene generata un'eccezione gestita.|  
  
 La tabella seguente mostra i dati degli eventi.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|Tipo di eccezione|win:UnicodeString|Tipo dell'eccezione, ad esempio `System.NullReferenceException`.|  
|Messaggio dell'eccezione|win:UnicodeString|Messaggio effettivo dell'eccezione.|  
|EIPCodeThrow|win:Pointer|Puntatore dell'istruzione in cui si è verificata l'eccezione.|  
|ExceptionHR|win:UInt32|[HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a) dell'eccezione.|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException. Vedere [CLR ETW Events](clr-etw-events.md) (Eventi ETW di CLR) nella documentazione di Visual Basic.<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (indica che lo stato del processo è danneggiato; vedere [gestione delle eccezioni di stato danneggiato](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).<br /><br /> 0x10: IsCLSCompliant. Un'eccezione derivante da <xref:System.Exception> è conforme a CLS. In caso contrario, non è conforme a CLS.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)
