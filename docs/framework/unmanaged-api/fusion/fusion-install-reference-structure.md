---
title: Struttura FUSION_INSTALL_REFERENCE
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
ms.openlocfilehash: 3859752fd92a76f3fef1ceced0e792109b65106a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108283"
---
# <a name="fusion_install_reference-structure"></a>Struttura FUSION_INSTALL_REFERENCE
Rappresenta un riferimento che un'applicazione esegue a un assembly installato dall'applicazione nell'Global Assembly Cache.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`cbSize`|Dimensioni in byte della struttura.|  
|`dwFlags`|Riservato per l'estendibilità futura. Questo valore deve essere 0 (zero).|  
|`guidScheme`|Entità che aggiunge il riferimento. Questo campo può avere uno dei valori seguenti:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: all'assembly viene fatto riferimento da un'applicazione che è stata installata usando il Microsoft Windows Installer. Il campo `szIdentifier` è impostato su `MSI`e il campo `szNonCanonicalData` è impostato su `Windows Installer`. Questo schema viene utilizzato per gli assembly side-by-side di Windows.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: all'assembly viene fatto riferimento da un'applicazione visualizzata nell'interfaccia **Installazione applicazioni** . Il campo `szIdentifier` fornisce il token che registra l'applicazione con l'interfaccia di **Installazione applicazioni** .<br />-FUSION_REFCOUNT_FILEPATH_GUID: all'assembly viene fatto riferimento da un'applicazione rappresentata da un file nel file system. Il campo `szIdentifier` fornisce il percorso del file.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID: all'assembly viene fatto riferimento da un'applicazione rappresentata solo da una stringa opaca. Il campo `szIdentifier` fornisce questa stringa opaca. Il Global Assembly Cache non verifica l'esistenza di riferimenti opachi quando si rimuove questo valore.<br />-FUSION_REFCOUNT_OSINSTALL_GUID: questo valore è riservato.|  
|`szIdentifier`|Stringa univoca che identifica l'applicazione che ha installato l'assembly nel Global Assembly Cache. Il valore dipende dal valore del campo `guidScheme`.|  
|`szNonCanonicalData`|Stringa riconosciuta solo dall'entità che aggiunge il riferimento. Il Global Assembly Cache archivia questa stringa, ma non la utilizza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture Fusion](fusion-structures.md)
- [Global Assembly Cache](../../app-domains/gac.md)
