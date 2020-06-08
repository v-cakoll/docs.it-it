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
ms.openlocfilehash: 901c62e6f2519fc4f9251f348c77b11bbe0992be
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504345"
---
# <a name="epolicyaction-enumeration"></a>Enumerazione EPolicyAction
Descrive le azioni dei criteri che l'host può impostare per le operazioni descritte da [EClrOperation](eclroperation-enumeration.md) ed errori descritti da [EClrFailure](eclrfailure-enumeration.md).  
  
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`eAbortThread`|Specifica che il Common Language Runtime (CLR) deve interrompere normalmente il thread. Un'interruzione normale include i tentativi di eseguire tutti i `finally` blocchi, i `catch` blocchi correlati a interruzioni di thread e i finalizzatori.|  
|`eDisableRuntime`|Specifica che CLR deve immettere uno stato disabilitato. Non è possibile eseguire ulteriori codice gestito nel processo interessato e i thread non possono accedere a CLR.|  
|`eExitProcess`|Specifica che CLR deve tentare un'uscita normale del processo, tra cui l'esecuzione di finalizzatori e l'esecuzione di operazioni di pulizia e registrazione.|  
|`eFastExitProcess`|Specifica che CLR deve uscire immediatamente dal processo, senza eseguire finalizzatori o eseguire operazioni di pulizia e registrazione. Tuttavia, la notifica viene inviata al debugger.|  
|`eNoAction`|Specifica che non deve essere eseguita alcuna azione.|  
|`eRudeAbortThread`|Specifica che CLR deve eseguire un'interruzione di thread scortese. `catch` `finally` Vengono eseguiti solo i blocchi e contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .|  
|`eRudeExitProcess`|Specifica che CLR deve uscire dal processo senza eseguire finalizzatori o operazioni di registrazione.|  
|`eRudeUnloadAppDomain`|Specifica che CLR deve eseguire uno scaricamento rude di <xref:System.AppDomain> . Vengono eseguiti solo i finalizzatori contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> . Analogamente, tutti i thread con questo <xref:System.AppDomain> nello stack ricevono un oggetto `ThreadAbortException` , ma `catch` `finally` vengono eseguiti solo i blocchi e contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .|  
|`eThrowException`|Specifica che deve essere generata un'eccezione appropriata per la condizione, ad esempio memoria insufficiente, overflow del buffer e così via.|  
|`eUnloadAppDomain`|Specifica che <xref:System.AppDomain> deve essere scaricato. CLR tenta di eseguire i finalizzatori.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host imposta le azioni dei criteri chiamando i metodi dell'interfaccia [ICLRPolicyManager](iclrpolicymanager-interface.md) . Per informazioni sulle interruzioni scortesi e aggraziate, vedere l'enumerazione [EClrOperation](eclroperation-enumeration.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](eclrfailure-enumeration.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Interfaccia IHostPolicyManager](ihostpolicymanager-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
