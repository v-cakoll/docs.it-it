---
title: Interfaccia IHostPolicyManager
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503939"
---
# <a name="ihostpolicymanager-interface"></a>Interfaccia IHostPolicyManager
Fornisce metodi che notificano all'host le azioni eseguite dal Common Language Runtime (CLR) in caso di interruzioni, timeout o errori.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo OnDefaultAction](ihostpolicymanager-ondefaultaction-method.md)|Notifica all'host che il CLR sta per eseguire l'azione predefinita specificata da una chiamata a [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in risposta a un'interruzione o a uno scaricamento di un thread <xref:System.AppDomain> .|  
|[Metodo OnFailure](ihostpolicymanager-onfailure-method.md)|Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione delle risorse o di recupero.|  
|[Metodo OnTimeout](ihostpolicymanager-ontimeout-method.md)|Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](eclrfailure-enumeration.md)
- [Enumerazione EClrOperation](eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](epolicyaction-enumeration.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
