---
title: Metodo IManagedObject::GetObjectIdentity
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d014d2900ea790f84331ed933143513ae9e63f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213493"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>Metodo IManagedObject::GetObjectIdentity
Ottiene l'identità dell'oggetto gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBSTRGUID`  
 [out] Puntatore al GUID del processo in cui risiede l'oggetto.  
  
 `AppDomainID`  
 [out] Un puntatore all'ID del dominio applicazione dell'oggetto.  
  
 `pCCW`  
 [out] Un puntatore all'indice dell'oggetto nella v-table COM classico.  
  
## <a name="remarks"></a>Note  
 L'identità di un oggetto gestito include GUID processo, ID di dominio dell'applicazione e l'indice dell'oggetto nella v-table COM classico.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
