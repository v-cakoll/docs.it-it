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
ms.openlocfilehash: c86786a34ff236fb57a1ea6bc4d00b9cd5c4a717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134891"
---
# <a name="igchostgetstats-method"></a>Metodo IGCHost::GetStats
Ottiene le statistiche per lo stato corrente del sistema di Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStats`  
 [in, out] Puntatore a una struttura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) che contiene le statistiche per lo stato corrente del sistema di Garbage Collection.  
  
## <a name="remarks"></a>Note  
 Le statistiche possono essere utilizzate da un sistema di allocazione intelligente per consentire il funzionamento del sistema Garbage Collection. Ad esempio, il sistema di allocazione può determinare, dopo aver esaminato le statistiche, che è necessario aggiungere altra memoria o forzare una raccolta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost. idl, GCHost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
