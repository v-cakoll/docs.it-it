---
title: Evento ETW di stack
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5dc23f5105b589d5b74c9ea6b7f40b84c2b04e6a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046164"
---
# <a name="stack-etw-event"></a>Evento ETW di stack
L'evento di stack deve essere usato in combinazione con altri eventi per generare analisi dello stack dopo la generazione di un evento. Viene registrato quando il provider di runtime è abilitato. Si tratto di un evento molto frequente perché viene generato ogni volta che viene generato un altro evento di runtime. Per questo motivo, è consigliabile usare questo evento con cautela.  
  
 La tabella seguente illustra la parola chiave e il livello Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`StackKeyword` (0x40000000)|LogAlways(0)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|82|In combinazione con altri eventi per generare analisi dello stack dopo un evento.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome campo|Tipo di dati|DESCRIZIONE|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:Uint16|Identificatore di runtime univoco.|  
|Reserved1|win:UInt8|Riservato.|  
|Reserved2|win:UInt8|Riservato.|  
|FrameCount|win:UInt32|Numero di frame nell'analisi dello stack.|  
|Stack|win:Pointer|Colonne di puntatori a istruzioni.|  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)
