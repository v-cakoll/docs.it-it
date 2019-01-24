---
title: Metodo IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83a1c03c209d68035b3615c83ec0ee13b94eb549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719950"
---
# <a name="igchostsetgcstartuplimits-method"></a>Metodo IGCHost::SetGCStartupLimits
Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.  
  
> [!IMPORTANT]
>  Inizia con il [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile impostare le dimensioni dei segmenti e dimensioni del numero massimo di generazioni 0 per i valori maggiori `DWORD` tramite il [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) (metodo).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `SegmentSize`  
 [in] Le dimensioni del segmento usato dal sistema di garbage collection.  
  
 `MaxGen0Size`  
 [in] La dimensione massima per la generazione 0.  
  
## <a name="remarks"></a>Note  
 Il `SetGCStartupLimits` metodo può essere chiamato una sola volta. Questi valori non possono essere modificati in un secondo momento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost.idl, GCHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
