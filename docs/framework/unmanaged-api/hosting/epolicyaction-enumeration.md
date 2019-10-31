---
title: Enumerazione EPolicyAction
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138236"
---
# <a name="epolicyaction-enumeration"></a>Enumerazione EPolicyAction
Descrive le azioni dei criteri che l'host può impostare per le operazioni descritte da [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) ed errori descritti da [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`eAbortThread`|Specifica che il Common Language Runtime (CLR) deve interrompere normalmente il thread. Un'interruzione normale include i tentativi di esecuzione di tutti i blocchi di `finally`, di eventuali blocchi `catch` correlati a interruzioni di thread e finalizzatori.|  
|`eDisableRuntime`|Specifica che CLR deve immettere uno stato disabilitato. Non è possibile eseguire ulteriori codice gestito nel processo interessato e i thread non possono accedere a CLR.|  
|`eExitProcess`|Specifica che CLR deve tentare un'uscita normale del processo, tra cui l'esecuzione di finalizzatori e l'esecuzione di operazioni di pulizia e registrazione.|  
|`eFastExitProcess`|Specifica che CLR deve uscire immediatamente dal processo, senza eseguire finalizzatori o eseguire operazioni di pulizia e registrazione. Tuttavia, la notifica viene inviata al debugger.|  
|`eNoAction`|Specifica che non deve essere eseguita alcuna azione.|  
|`eRudeAbortThread`|Specifica che CLR deve eseguire un'interruzione di thread scortese. Vengono eseguiti solo i blocchi `catch` e `finally` contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.|  
|`eRudeExitProcess`|Specifica che CLR deve uscire dal processo senza eseguire finalizzatori o operazioni di registrazione.|  
|`eRudeUnloadAppDomain`|Specifica che CLR deve eseguire uno scaricamento rude del <xref:System.AppDomain>. Vengono eseguiti solo i finalizzatori contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>. Analogamente, tutti i thread con questo <xref:System.AppDomain> nello stack ricevono una `ThreadAbortException`, ma vengono eseguiti solo i blocchi `catch` e `finally` contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.|  
|`eThrowException`|Specifica che deve essere generata un'eccezione appropriata per la condizione, ad esempio memoria insufficiente, overflow del buffer e così via.|  
|`eUnloadAppDomain`|Specifica che il <xref:System.AppDomain> deve essere scaricato. CLR tenta di eseguire i finalizzatori.|  
  
## <a name="remarks"></a>Note  
 L'host imposta le azioni dei criteri chiamando i metodi dell'interfaccia [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) . Per informazioni sulle interruzioni scortesi e aggraziate, vedere l'enumerazione [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
