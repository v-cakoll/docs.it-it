---
title: Eventi ETW di conflitto
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
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 931a3f7d5cbc441a3cae2b7359d129dff02afd44
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="contention-etw-events"></a>Eventi ETW di conflitto
Gli eventi di conflitto vengono generati ogni volta che si verifica un conflitto per i blocchi <xref:System.Threading.Monitor?displayProperty=fullName> o nativi usati dal runtime. Un conflitto si verifica quando un thread attende un blocco mentre un altro thread possiede tale blocco.  
  
 La tabella seguente illustra le parole chiave con cui vengono generati gli eventi e il livello degli eventi stessi. Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Livello|  
|-----------------------------------|-----------|  
|`ContentionKeyword` (0x4000)|Informativo (4)|  
  
 La tabella seguente offre informazioni sull'evento.  
  
|Evento|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|81|Inizio del conflitto. Questo evento non include il tempo di rotazione che intercorre prima che un thread attenda l'acquisizione di un blocco; viene generato soltanto quando il thread attende di acquisire un blocco.|  
|`ContentionStop`|81|Fine del conflitto.|  
  
 La tabella seguente mostra i dati degli eventi.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|Flag|win:UInt8|0 per gestito, 1 per nativo.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR.|  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md)

