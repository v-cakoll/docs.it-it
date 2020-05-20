---
title: Interfaccia ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703557"
---
# <a name="iclriocompletionmanager-interface"></a>Interfaccia ICLRIoCompletionManager
Implementa un metodo di callback che consente all'host di notificare al Common Language Runtime (CLR) lo stato delle richieste di I/O specificate.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Notifica a CLR lo stato di una richiesta di I/O effettuata mediante una chiamata al metodo [IHostIoCompletionManager:: bind](ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Osservazioni  
 L'host implementa l'astrazione di completamento I/O usando l'interfaccia [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) . CLR esegue richieste di I/O tramite questa interfaccia e l'host notifica al runtime il risultato di tali richieste usando l' `ICLRIoCompletionManager` interfaccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
- [Interfaccia IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
