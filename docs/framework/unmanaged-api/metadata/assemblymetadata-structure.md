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
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444263"
---
# <a name="assemblymetadata-structure"></a>Struttura ASSEMBLYMETADATA
Contiene informazioni sull'assembly a cui si fa riferimento, incluse la versione e il livello di supporto per le impostazioni locali, i processori e i sistemi operativi.  
  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`usMajorVersion`|Numero di versione principale dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se vengono impostati tutti i bit di `usMajorVersion`, la versione principale non è specificata.|  
|`usMinorVersion`|Numero della versione secondaria dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se vengono impostati tutti i bit di `usMinorVersion`, non viene specificata la versione secondaria.|  
|`usBuildNumber`|Numero di build dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se vengono impostati tutti i bit di `usBuildNumber`, il numero di build non viene specificato.|  
|`usRevisionNumber`|Numero di revisione dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se vengono impostati tutti i bit di `usRevisionNumber`, il numero di revisione non viene specificato.|  
|`szLocale`|Elenco di nomi delle impostazioni locali conformi alla specifica RFC1766, separati da punti e virgola, che specificano le impostazioni locali supportate dall'assembly a cui si fa riferimento. Un valore null indica l'indipendenza delle impostazioni locali. **Nota:**  In .NET Framework versione 1,0 non è possibile specificare più di un'impostazione locale.|  
|`cbLocale`|Dimensioni in caratteri wide di `szLocale`.|  
|`rdwProcessor`|Matrice di identificatori, in base a quanto definito in Winnt. h, per i tipi di processore supportati dall'assembly a cui si fa riferimento. Un valore NULL indica l'indipendenza del processore.|  
|`ulProcessor`|Lunghezza della matrice di `rdwProcessor`.|  
|`rOS`|Matrice di istanze di [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) che specifica i sistemi operativi supportati dall'assembly a cui si fa riferimento. Un valore NULL indica l'indipendenza del sistema operativo.|  
|`ulOS`|Lunghezza della matrice di `rOS`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Struttura OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
