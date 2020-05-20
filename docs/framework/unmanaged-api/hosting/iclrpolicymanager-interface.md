---
title: Interfaccia ICLRPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 631301a10aee96bb00aeda6b0b8695f0aea186a8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703485"
---
# <a name="iclrpolicymanager-interface"></a>Interfaccia ICLRPolicyManager
Fornisce metodi che consentono all'host di specificare le azioni dei criteri da intraprendere in caso di errori e timeout.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md)|Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'errore specificato.|  
|[Metodo SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)|Specifica l'azione del criterio che CLR deve eseguire quando si verifica il timeout dell'operazione specificata.|  
|[Metodo SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md)|Specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione specificata.|  
|[Metodo SetTimeout](iclrpolicymanager-settimeout-method.md)|Imposta un valore di timeout per l'operazione specificata.|  
|[Metodo SetTimeoutAndAction](iclrpolicymanager-settimeoutandaction-method.md)|Imposta un valore di timeout per l'operazione specificata e specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione.|  
|[Metodo SetUnhandledExceptionPolicy](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](eclrfailure-enumeration.md)
- [Enumerazione EClrOperation](eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](epolicyaction-enumeration.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
