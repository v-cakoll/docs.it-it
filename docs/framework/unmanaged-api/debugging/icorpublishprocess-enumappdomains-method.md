---
title: Metodo ICorPublishProcess::EnumAppDomains
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: 0c3b5da52b78150198fa9f910bf01b4657e4eba8
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421163"
---
# <a name="icorpublishprocessenumappdomains-method"></a>Metodo ICorPublishProcess::EnumAppDomains
Ottiene un enumeratore per i domini applicazione nel processo a cui fa riferimento questo [ICorPublishProcess](icorpublishprocess-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEnum`  
 out Puntatore all'indirizzo di un'istanza di [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) che consente l'iterazione nella raccolta di domini applicazione in questo processo.  
  
## <a name="remarks"></a>Osservazioni  
 L'elenco dei domini applicazione si basa su uno snapshot dei domini applicazione esistenti quando `EnumAppDomains` viene chiamato il metodo. Questo metodo può essere chiamato più volte per creare un nuovo elenco aggiornato. Gli elenchi esistenti non saranno interessati dalle chiamate successive di questo metodo.  
  
 Se il processo è stato terminato, `EnumAppDomains` avrà esito negativo con un valore HRESULT pari a CORDBG_E_PROCESS_TERMINATED.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorPublishProcess](icorpublishprocess-interface.md)
