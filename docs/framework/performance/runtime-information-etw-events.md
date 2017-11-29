---
title: Eventi ETW di informazione di runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime information events [.NET Framework]
- ETW, runtime information events
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9a01b1f47969d7ddec250fa8bcafe5e1a851b5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="runtime-information-etw-events"></a>Eventi ETW di informazione di runtime
Questi eventi ETW registrano informazioni sul runtime, inclusi lo SKU, il numero della versione, la modalità di attivazione del runtime, i parametri della riga di comando con cui è stato avviato il runtime, il GUID (se applicabile) e altre informazioni rilevanti. Se più runtime sono in esecuzione all'interno di un processo, le informazioni fornite da questi eventi (ClrInstanceID) consentono di distinguere tra i runtime.  
  
 La tabella seguente mostra i due eventi di informazioni sui runtime. Gli eventi possono essere generati con qualsiasi parola chiave o maschera. Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).  
  
|Evento|ID evento|Provider|Descrizione|  
|-----------|--------------|--------------|-----------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Generato quando viene caricato un runtime.|  
|`RuntimeInformationDCStart`|187|CLRRundown|Enumera i runtime caricati.|  
  
 La tabella seguente mostra i dati degli eventi.  
  
|Nome campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
|Sku|win:UInt16|1 - CLR desktop.<br /><br /> 2 - CoreCLR.|  
|BclVersion – Major Version|win:UInt16|Versione principale di mscorlib.dll.|  
|BclVersion – Minor Version|win:UInt16|Numero della versione secondaria di mscorlib.dll.|  
|BclVersion – Build Number|win:UInt16|Numero di build di mscorlib.dll.|  
|BclVersion – QFE|win:UInt16|Numero della versione hotfix di mscorlib.dll.|  
|VMVersion – Major Version|win:UInt16|Versione di clr.dll o coreclr.dll, a seconda dello SKU.|  
|VMVersion – Minor Version|win:UInt16|Versione secondaria di clr.dll o coreclr.dll, a seconda dello SKU.|  
|VMVersion – Build Number|win:UInt16|Numero di build di clr.dll o coreclr.dll.|  
|VMVersion – QFE|win:UInt16|Numero della versione hotfix di clr.dll o coreclr.dll.|  
|StartupFlags|win:UInt32|Flag di avvio definiti in mscoree.h.|  
|StartupMode|win:UInt8|0x01 - Eseguibile gestito.<br /><br /> 0x02 - CLR ospitato.<br /><br /> 0x04 - Interoperabilità gestita C++.<br /><br /> 0x08 - Attivazione COM.<br /><br /> 0x10 - Altro.|  
|CommandLine|win:UnicodeString|Non Null solo se StartupMode=0x01.|  
|ComObjectGUID|win:GUID|Non Null solo se StartupMode=0x08.|  
|RuntimeDLLPath|win:UnicodeString|Percorso del file DLL CLR che è stato caricato nel processo.|  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md)
