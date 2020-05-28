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
ms.openlocfilehash: 5c7211fc2523b70313a1e4d4d9d2da0dcecd1d32
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009431"
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
|`usMajorVersion`|Numero di versione principale dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se tutti i bit di `usMajorVersion` sono impostati, la versione principale non è specificata.|  
|`usMinorVersion`|Numero della versione secondaria dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se tutti i bit di `usMinorVersion` sono impostati, la versione secondaria non è specificata.|  
|`usBuildNumber`|Numero di build dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se tutti i bit di `usBuildNumber` sono impostati, il numero di build non viene specificato.|  
|`usRevisionNumber`|Numero di revisione dell'assembly a cui si fa riferimento. Questo valore non può essere zero. Se tutti i bit di `usRevisionNumber` sono impostati, il numero di revisione non viene specificato.|  
|`szLocale`|Elenco di nomi delle impostazioni locali conformi alla specifica RFC1766, separati da punti e virgola, che specificano le impostazioni locali supportate dall'assembly a cui si fa riferimento. Un valore null indica l'indipendenza delle impostazioni locali. **Nota:**  In .NET Framework versione 1,0 non è possibile specificare più di un'impostazione locale.|  
|`cbLocale`|Dimensioni in caratteri wide di `szLocale` .|  
|`rdwProcessor`|Matrice di identificatori, in base a quanto definito in Winnt. h, per i tipi di processore supportati dall'assembly a cui si fa riferimento. Un valore NULL indica l'indipendenza del processore.|  
|`ulProcessor`|Lunghezza della matrice `rdwProcessor`.|  
|`rOS`|Matrice di istanze di [OSINFO](osinfo-structure.md) che specifica i sistemi operativi supportati dall'assembly a cui si fa riferimento. Un valore NULL indica l'indipendenza del sistema operativo.|  
|`ulOS`|Lunghezza della matrice `rOS`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di metadati](metadata-structures.md)
- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Struttura OSINFO](osinfo-structure.md)
