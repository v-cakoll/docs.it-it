---
title: Struttura ASSEMBLYMETADATA
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5039117c649943a1f05a91ecccf22eb4230e5e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776382"
---
# <a name="assemblymetadata-structure"></a>Struttura ASSEMBLYMETADATA
Contiene informazioni sull'assembly di riferimento, inclusi la versione e del relativo livello di supporto per le impostazioni locali, processori e sistemi operativi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`usMajorVersion`|Il numero di versione principale dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usMajorVersion` vengono impostate, la versione principale non è specificata.|  
|`usMinorVersion`|Il numero di versione secondaria dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usMinorVersion` vengono impostate, la versione secondaria non è specificata.|  
|`usBuildNumber`|Il numero di build dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usBuildNumber` vengono impostate, il numero di build non è specificato.|  
|`usRevisionNumber`|Il numero di revisione dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usRevisionNumber` vengono impostate, il numero di revisione non è specificato.|  
|`szLocale`|Elenco di nomi delle impostazioni locali conforme alla specifica RFC1766, separata da punti e virgola, che specifica le impostazioni locali supportate dall'assembly cui viene fatto riferimento. Un valore null indica l'indipendenza dalle impostazioni locali. **Nota:**  In .NET Framework versione 1.0 non è possibile specificare più di una delle impostazioni locali.|  
|`cbLocale`|La dimensione in caratteri "wide" di `szLocale`.|  
|`rdwProcessor`|Matrice di identificatori, come definito in Winnt. h, per i tipi di processore supportati da assembly di riferimento. Un valore NULL indica l'indipendenza del processore.|  
|`ulProcessor`|La lunghezza del `rdwProcessor` matrice.|  
|`rOS`|Matrice di [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) istanze che specifica i sistemi operativi supportati da assembly di riferimento. Un valore NULL indica l'indipendenza del sistema operativo.|  
|`ulOS`|La lunghezza del `rOS` matrice.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Struttura OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
