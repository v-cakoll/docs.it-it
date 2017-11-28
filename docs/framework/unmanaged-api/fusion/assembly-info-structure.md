---
title: Struttura ASSEMBLY_INFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a>Struttura ASSEMBLY_INFO
Contiene informazioni relative a un assembly registrato nella global assembly cache.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`cbAssemblyInfo`|Le dimensioni in byte, della struttura. Questo campo è riservato per l'estensibilità futura.|  
|`dwAssemblyFlags`|Flag che indicano i dettagli di installazione sull'assembly. Sono supportati i seguenti valori:<br /><br /> -Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è installato. Imposta sempre la versione corrente di .NET Framework `dwAssemblyFlags` su questo valore.<br />-Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è un payload residente. La versione corrente di .NET Framework non viene mai `dwAssemblyFlags` su questo valore.|  
|`uliAssemblySizeInKB`|Dimensione totale, espressa in kilobyte, dei file che contiene l'assembly.|  
|`pszCurrentAssemblyPathBuf`|Puntatore a un buffer di stringa che contiene il percorso corrente nel file manifesto. Il percorso deve terminare con un carattere null.|  
|`cchBuf`|Il numero di caratteri wide, incluso il terminatore null, che `pszCurrentAssemblyPathBuf` contiene.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Global Assembly Cache](../../../../docs/framework/app-domains/gac.md)
