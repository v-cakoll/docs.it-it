---
title: Metodo IGCHost2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5e90055a08227ea7cb7fa1b459fe6f5f3a81fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127335"
---
# <a name="igchost2setgcstartuplimitsex-method"></a>Metodo IGCHost2::SetGCStartupLimitsEx
Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `SegmentSize`  
 [in] Le dimensioni del segmento usato dal sistema di garbage collection.  
  
 `MaxGen0Size`  
 [in] La dimensione massima per la generazione 0.  
  
## <a name="remarks"></a>Note  
 I valori che `SetGCStartupLimitsEx` set possono essere specificati solo prima dell'avvio dell'host. Questi valori non possono essere modificati in un secondo momento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost.idl, GCHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IGCHost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
