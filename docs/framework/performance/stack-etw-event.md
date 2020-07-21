---
title: Evento ETW di stack
description: Informazioni sull'evento ETW dello stack, che deve essere usato insieme ad altri eventi per generare le analisi dello stack dopo la generazione di un evento.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: cab496615c4ef17831895b72c8987917e3c06e77
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474137"
---
# <a name="stack-etw-event"></a>Evento ETW di stack
L'evento di stack deve essere usato in combinazione con altri eventi per generare analisi dello stack dopo la generazione di un evento. Viene registrato quando il provider di runtime è abilitato. Si tratto di un evento molto frequente perché viene generato ogni volta che viene generato un altro evento di runtime. Per questo motivo, è consigliabile usare questo evento con cautela.  
  
 La tabella seguente illustra la parola chiave e il livello Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Level|  
|-----------------------------------|-----------|  
|`StackKeyword` (0x40000000)|LogAlways(0)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Evento|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|82|In combinazione con altri eventi per generare analisi dello stack dopo un evento.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:Uint16|Identificatore di runtime univoco.|  
|Reserved1|win:UInt8|Riservato.|  
|Reserved2|win:UInt8|Riservato.|  
|FrameCount|win:UInt32|Numero di frame nell'analisi dello stack.|  
|Stack|win:Pointer|Colonne di puntatori a istruzioni.|  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)
