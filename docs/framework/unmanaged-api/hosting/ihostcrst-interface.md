---
title: Interfaccia IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: e8cb1486ccea11ba6edcf7bbb781a9bf210b496d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804907"
---
# <a name="ihostcrst-interface"></a>Interfaccia IHostCrst
Funge da rappresentazione dell'host di una sezione critica per il Threading.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Enter](ihostcrst-enter-method.md)|Immette la sezione critica.|  
|[Metodo Leave](ihostcrst-leave-method.md)|Lascia la sezione critica.|  
|[Metodo SetSpinCount](ihostcrst-setspincount-method.md)|Imposta il numero di spin per la sezione critica.|  
|[Metodo TryEnter](ihostcrst-tryenter-method.md)|Tenta di immettere la sezione critica e segnala immediatamente l'esito positivo o negativo.|  
  
## <a name="remarks"></a>Osservazioni  
 `IHostCrst`consente all'Common Language Runtime (CLR) di comunicare direttamente con la rappresentazione dell'host di una sezione critica, anziché usare funzioni Win32 come `EnterCriticalSection` o `LeaveCriticalSection` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interfaccia IHostSyncManager](ihostsyncmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
