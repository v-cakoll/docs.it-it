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
ms.workload: dotnet
ms.openlocfilehash: 2c0d09bf4c24f977a490f946cbc35b2b3f53dfc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
 [Interfaccia IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [Struttura IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [Strutture Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
