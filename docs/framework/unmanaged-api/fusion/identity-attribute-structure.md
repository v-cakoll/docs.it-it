---
title: Struttura IDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de1646cdbc11369b43a821d8b762879d1df7ed2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751543"
---
# <a name="identityattribute-structure"></a>Struttura IDENTITY_ATTRIBUTE
Contiene informazioni sugli attributi di metadati su un' [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) istanza.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`pszNamespace`|Un puntatore a una stringa di caratteri con terminazione null che contiene lo spazio dei nomi dell'attributo è in.|  
|`pszName`|Un puntatore a una stringa di caratteri con terminazione null che contiene il nome dell'attributo.|  
|`pszValue`|Un puntatore a una stringa di caratteri con terminazione null che contiene il valore dell'attributo.|  
  
## <a name="remarks"></a>Note  
 Il `IDENTITY_ATTRIBUTE` struttura contiene tre puntatori a stringhe di caratteri con terminazione null. Queste tre stringhe descrivono un attributo.  
  
 Un'istanza di un `IDENTITY_ATTRIBUTE` struttura è associata a un'istanza di un [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) struttura. Il `IDENTITY_ATTRIBUTE` struttura contiene le stringhe effettive e il corrispondente `IDENTITY_ATTRIBUTE_BLOB` struttura Elenca gli offset per le tre stringhe elencate nella `IDENTITY_ATTRIBUTE` struttura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [Struttura IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [Strutture Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
