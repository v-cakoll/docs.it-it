---
title: Metodo IGCHost::GetStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9a3775f453cb432ce6b92d067f93ca54c329c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674180"
---
# <a name="igchostgetstats-method"></a>Metodo IGCHost::GetStats
Ottiene le statistiche per lo stato corrente del sistema di garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pStats`  
 [in, out] Un puntatore a un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) struttura che contiene le statistiche per lo stato corrente del sistema di garbage collection.  
  
## <a name="remarks"></a>Note  
 Le statistiche possono essere utilizzate da un sistema di assegnazione intelligente per agevolare il sistema di garbage collection di corretto funzionamento. Ad esempio, il sistema di allocazione può determinare, dopo aver esaminato le statistiche, è necessario aggiungere ulteriore memoria o forzare una raccolta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost.idl, GCHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
