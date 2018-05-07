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
ms.openlocfilehash: cbe94aa67c9cf9ac587b7fca9f5cbeca4870506b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="igchostsetgcstartuplimits-method"></a>Metodo IGCHost::SetGCStartupLimits
Imposta le dimensioni del segmento e la dimensione massima per la generazione 0.  
  
> [!IMPORTANT]
>  A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile impostare una dimensione del segmento e dimensione massima di generazione 0 a valori maggiori di `DWORD` utilizzando il [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `SegmentSize`  
 [in] Dimensione del segmento utilizzata dal sistema di garbage collection.  
  
 `MaxGen0Size`  
 [in] La dimensione massima per la generazione 0.  
  
## <a name="remarks"></a>Note  
 Il `SetGCStartupLimits` metodo può essere chiamato una sola volta. Questi valori non possono essere modificati successivamente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost. idl, GCHost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
