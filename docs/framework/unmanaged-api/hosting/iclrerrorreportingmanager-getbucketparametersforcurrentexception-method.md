---
title: Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec7e303e5145e16f4c17074d557410ffe4521c20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549837"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a>Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException
Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.  
  
 Oggetto *bucket* è una raccolta di dati di errore che sono correlati il difetto del codice stesso. *Watson* fa riferimento a un set di tecnologie per la raccolta e analisi dei dati che sono associati a un'eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pParams`  
 [out] Un puntatore a un [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) struttura che contiene i dati di errore per l'eccezione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
