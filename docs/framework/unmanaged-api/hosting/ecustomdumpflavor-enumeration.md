---
title: Enumerazione ECustomDumpFlavor
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1e69d9cbf39049e82803d2f7bc795cc9fd0b368
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154440"
---
# <a name="ecustomdumpflavor-enumeration"></a>Enumerazione ECustomDumpFlavor
Contiene valori che indicano gli elementi da includere in un subset di un heap personalizzato di dump quando si segnalano errori.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Specifica che il dump dell'heap personalizzato deve avviare come un minidump e include dati extra specificati da qualsiasi [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) istanze passato al metodo di stesso.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Specifica che il dump dell'heap personalizzato deve raccogliere tutti i dati di stato di runtime che non è stati allocati in modo dinamico.|  
  
## <a name="remarks"></a>Note  
 Un parametro di tipo `ECustomDumpFlavor` viene passato per il [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [Interfaccia ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
