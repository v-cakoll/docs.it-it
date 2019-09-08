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
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796494"
---
# <a name="identity_attribute-structure"></a>Struttura IDENTITY_ATTRIBUTE
Contiene informazioni sugli attributi di metadati relativi a un'istanza di [IDefinitionIdentity](idefinitionidentity-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Members  
  
|Member|DESCRIZIONE|  
|------------|-----------------|  
|`pszNamespace`|Puntatore a una stringa di caratteri con terminazione null che contiene lo spazio dei nomi in cui si trova l'attributo.|  
|`pszName`|Puntatore a una stringa di caratteri con terminazione null che contiene il nome dell'attributo.|  
|`pszValue`|Puntatore a una stringa di caratteri con terminazione null che contiene il valore dell'attributo.|  
  
## <a name="remarks"></a>Note  
 La `IDENTITY_ATTRIBUTE` struttura contiene tre puntatori a stringhe di caratteri con terminazione null. Queste tre stringhe descrivono un attributo.  
  
 Un'istanza di una `IDENTITY_ATTRIBUTE` struttura è associata a un'istanza di una struttura [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) . La `IDENTITY_ATTRIBUTE` struttura contiene le stringhe effettive e la struttura `IDENTITY_ATTRIBUTE_BLOB` corrispondente elenca gli offset alle `IDENTITY_ATTRIBUTE` tre stringhe elencate nella struttura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IDefinitionIdentity](idefinitionidentity-interface.md)
- [Struttura IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md)
- [Strutture Fusion](fusion-structures.md)
