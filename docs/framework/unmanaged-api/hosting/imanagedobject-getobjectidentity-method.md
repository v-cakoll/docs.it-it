---
title: Metodo IManagedObject::GetObjectIdentity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c5654865c557e6e004685f66753366d7cb575919
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parametri  
 `pBSTRGUID`  
 [out] Puntatore al GUID del processo in cui si trova l'oggetto.  
  
 `AppDomainID`  
 [out] Un puntatore all'ID del dominio applicazione dell'oggetto.  
  
 `pCCW`  
 [out] Un puntatore all'indice dell'oggetto nella v-table COM classico.  
  
## <a name="remarks"></a>Note  
 L'identità di un oggetto gestito include l'indice dell'oggetto processo GUID e ID di dominio di applicazione nella v-table COM classico.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
