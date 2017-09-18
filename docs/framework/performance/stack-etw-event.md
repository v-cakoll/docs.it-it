---
title: Evento ETW di stack
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: 5
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 55219fe755f49b6edbd3b53cc686bf4f9087aa08
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="stack-etw-event"></a>Evento ETW di stack
L'evento di stack deve essere usato in combinazione con altri eventi per generare analisi dello stack dopo la generazione di un evento. Viene registrato quando il provider di runtime è abilitato. Si tratto di un evento molto frequente perché viene generato ogni volta che viene generato un altro evento di runtime. Per questo motivo, è consigliabile usare questo evento con cautela.  
  
 La tabella seguente illustra la parola chiave e il livello Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Livello|  
|-----------------------------------|-----------|  
|`StackKeyword` (0x40000000)|LogAlways(0)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Evento|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|82|In combinazione con altri eventi per generare analisi dello stack dopo un evento.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:Uint16|Identificatore di runtime univoco.|  
|Reserved1|win:UInt8|Riservato.|  
|Reserved2|win:UInt8|Riservato.|  
|FrameCount|win:UInt32|Numero di frame nell'analisi dello stack.|  
|Stack|win:Pointer|Colonne di puntatori a istruzioni.|  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md)

