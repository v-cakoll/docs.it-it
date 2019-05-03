---
title: Eventi ETW di informazione di runtime
ms.date: 03/30/2017
helpviewer_keywords:
- runtime information events [.NET Framework]
- ETW, runtime information events
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af27ddaa69d34976929f40055bc2cc668f877e87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949214"
---
# <a name="runtime-information-etw-events"></a>Eventi ETW di informazione di runtime
Questi eventi ETW registrano informazioni sul runtime, inclusi lo SKU, il numero della versione, la modalità di attivazione del runtime, i parametri della riga di comando con cui è stato avviato il runtime, il GUID (se applicabile) e altre informazioni rilevanti. Se più runtime sono in esecuzione all'interno di un processo, le informazioni fornite da questi eventi (ClrInstanceID) consentono di distinguere tra i runtime.  
  
 La tabella seguente mostra i due eventi di informazioni sui runtime. Gli eventi possono essere generati con qualsiasi parola chiave o maschera. Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).  
  
|event|ID evento|Provider|Descrizione|  
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

- [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md)
