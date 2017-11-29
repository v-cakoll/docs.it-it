---
title: Struttura IDENTITY_ATTRIBUTE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE
helpviewer_keywords: IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3fc4d9f7a95a3283d87f036163592f43e87dd053
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="identityattribute-structure"></a>Struttura IDENTITY_ATTRIBUTE
Contiene informazioni sugli attributi di metadati su un [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) istanza.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`pszNamespace`|Un puntatore a una stringa di caratteri con terminazione null che contiene lo spazio dei nomi cui è l'attributo.|  
|`pszName`|Un puntatore a una stringa di caratteri con terminazione null che contiene il nome dell'attributo.|  
|`pszValue`|Un puntatore a una stringa di caratteri con terminazione null che contiene il valore dell'attributo.|  
  
## <a name="remarks"></a>Note  
 Il `IDENTITY_ATTRIBUTE` struttura contiene tre puntatori alle stringhe di caratteri con terminazione null. Queste tre stringhe descrivono un attributo.  
  
 Un'istanza di un `IDENTITY_ATTRIBUTE` struttura è associata a un'istanza di un [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) struttura. Il `IDENTITY_ATTRIBUTE` struttura contiene le stringhe effettive e i corrispondenti `IDENTITY_ATTRIBUTE_BLOB` struttura sono elencati gli offset alle tre stringhe elencate nella `IDENTITY_ATTRIBUTE` struttura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IDefinitionIdentity (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [IDENTITY_ATTRIBUTE_BLOB (struttura)](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [Strutture Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
