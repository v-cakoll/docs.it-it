---
title: Struttura OSINFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd30fe7904fa6c0685dd9c39931cc545e4e30583
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="osinfo-structure"></a>Struttura OSINFO
Contiene i dettagli sul sistema operativo per un assembly o un modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`dwOSPlatformId`|Uno dei valori di identificatore definiti dalla funzione piattaforma Microsoft Windows `GetVersionEx`. Sono supportati i seguenti valori:<br /><br /> -VER_PLATFORM_WIN32s, o 0x0000 per specificare Microsoft Windows 3.1.<br />-VER_PLATFORM_WIN32_WINDOWS, o 0x0001 per specificare Windows 95, Windows 98 o sistemi operativi discendenti.<br />-VER_PLATFORM_WIN32_NT, o 0x0010 per specificare i sistemi operativi o Windows NT discendenti.|  
|`dwOSMajorVersion`|La versione principale sistema operativo, o un valore NULL per indicare qualsiasi versione.|  
|`dwOSMinorVersion`|La versione secondaria del sistema operativo, o un valore NULL per indicare qualsiasi versione.|  
  
## <a name="remarks"></a>Note  
 `OSINFO`si basa sul `OSVERSIONINFOEX` struttura utilizzati nelle chiamate alla funzione piattaforma Microsoft Windows `GetVersionEx`. Questa struttura è utilizzata dalla struttura ASSEMBLYMETADATA per indicare il supporto del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
