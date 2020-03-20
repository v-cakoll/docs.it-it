---
title: Struttura OSINFO
ms.date: 03/30/2017
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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175226"
---
# <a name="osinfo-structure"></a>Struttura OSINFO
Contiene dettagli sul sistema operativo per un assembly o un modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`dwOSPlatformId`|Uno dei valori dell'identificatore definiti `GetVersionEx`dalla funzione della piattaforma Microsoft Windows . Sono supportati i valori seguenti:<br /><br /> - VER_PLATFORM_WIN32s, o 0x0000, per specificare Microsoft Windows 3.1.<br />- VER_PLATFORM_WIN32_WINDOWS, o 0x0001, per specificare Windows 95, Windows 98 o sistemi operativi discendenti da essi.<br />- VER_PLATFORM_WIN32_NT, o 0x0002, per specificare Windows NT o sistemi operativi discendenti da esso.|  
|`dwOSMajorVersion`|La versione principale del sistema operativo o un valore NULL per indicare qualsiasi versione.|  
|`dwOSMinorVersion`|Versione secondaria del sistema operativo o valore NULL per indicare qualsiasi versione.|  
  
## <a name="remarks"></a>Osservazioni  
 `OSINFO`si basa `OSVERSIONINFOEX` sulla struttura utilizzata nelle chiamate alla `GetVersionEx`funzione della piattaforma Microsoft Windows . Questa struttura viene utilizzata dalla struttura ASSEMBLYMETADATA per indicare il supporto del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
