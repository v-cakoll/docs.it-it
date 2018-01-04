---
title: Struttura ASSEMBLYMETADATA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLYMETADATA
api_location: mscoree.dll
api_type: COM
f1_keywords: ASSEMBLYMETADATA
helpviewer_keywords: ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 819510c14bd67e7fcc739a19ea945f16b2a66c9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="assemblymetadata-structure"></a>Struttura ASSEMBLYMETADATA
Contiene informazioni sull'assembly di riferimento, tra cui la versione e il livello di supporto per le impostazioni locali, processori e sistemi operativi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`usMajorVersion`|Il numero di versione principale dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usMajorVersion` sono impostati, la versione principale non è specificata.|  
|`usMinorVersion`|Il numero di versione secondaria dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usMinorVersion` sono impostati, la versione secondaria non è specificata.|  
|`usBuildNumber`|Il numero di build dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usBuildNumber` sono impostati, il numero di build non è specificato.|  
|`usRevisionNumber`|Il numero di revisione dell'assembly di riferimento. Questo valore non può essere zero. Se tutti i bit di `usRevisionNumber` sono impostati, non viene specificato il numero di revisione.|  
|`szLocale`|Un elenco di nomi delle impostazioni locali conformi alle specifiche RFC1766, separati da punti e virgola, che specifica le impostazioni locali supportate dall'assembly di riferimento. Un valore null indica l'indipendenza dalle impostazioni locali. **Nota:** In .NET Framework versione 1.0 non è possibile specificare più di una lingua.|  
|`cbLocale`|La dimensione in caratteri "wide" di `szLocale`.|  
|`rdwProcessor`|Matrice di identificatori, come definito in Winnt. h, per i tipi di processore supportati da assembly di riferimento. Un valore NULL indica l'indipendenza del processore.|  
|`ulProcessor`|La lunghezza del `rdwProcessor` matrice.|  
|`rOS`|Matrice di [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) istanze che specifica i sistemi operativi supportati da assembly di riferimento. Un valore NULL indica l'indipendenza del sistema operativo.|  
|`ulOS`|La lunghezza del `rOS` matrice.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [Struttura OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
