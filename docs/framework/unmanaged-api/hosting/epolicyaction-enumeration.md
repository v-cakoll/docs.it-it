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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14908ae641c8539659e6014deb2c5f35a6d1cfbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433630"
---
# <a name="epolicyaction-enumeration"></a>Enumerazione EPolicyAction
Descrive le azioni dei criteri dell'host è possibile impostare per le operazioni specificate da [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) e gli errori indicati da [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|`eAbortThread`|Specifica che common language runtime (CLR) deve interrompere il thread normalmente. Interruzione di una normale include i tentativi di eseguire tutti `finally` si blocca, qualsiasi `catch` i blocchi correlati alle interruzioni del thread e i finalizzatori.|  
|`eDisableRuntime`|Specifica che Common Language Runtime deve essere stato disabilitato. Senza ulteriore codice gestito può essere eseguito nel processo interessato, e i thread sono bloccati da rientrano nel CLR.|  
|`eExitProcess`|Specifica che Common Language Runtime deve tentare una valida uscita del processo, eseguendo i finalizzatori e l'esecuzione di operazioni di registrazione e di pulizia.|  
|`eFastExitProcess`|Specifica che Common Language Runtime si chiude il processo immediatamente, senza l'esecuzione dei finalizzatori o esecuzione di operazioni di registrazione e di pulizia. Nowever, notifica viene inviata al debugger.|  
|`eNoAction`|Specifica che deve essere eseguita alcuna azione.|  
|`eRudeAbortThread`|Specifica che Common Language Runtime deve eseguire un'interruzione del thread in modo irregolare. Solo quelli `catch` e `finally` blocchi contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> vengono eseguite.|  
|`eRudeExitProcess`|Specifica che Common Language Runtime deve uscire dal processo senza esecuzione dei finalizzatori o operazioni di registrazione.|  
|`eRudeUnloadAppDomain`|Specifica che Common Language Runtime deve eseguire uno scaricamento non regolare del <xref:System.AppDomain>. Solo i finalizzatori contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> vengono eseguite. Allo stesso modo, tutti i thread con questo <xref:System.AppDomain> nei relativi stack ricevere un `ThreadAbortException`, ma solo quelle `catch` e `finally` blocchi contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> vengono eseguite.|  
|`eThrowException`|Specifica che deve essere generata un'eccezione appropriata alla condizione, ad esempio di memoria insufficiente, overflow del buffer e così via.|  
|`eUnloadAppDomain`|Specifica che il <xref:System.AppDomain> deve essere scaricato. Common Language Runtime tenta di eseguire i finalizzatori.|  
  
## <a name="remarks"></a>Note  
 L'host imposta le azioni dei criteri chiamando i metodi del [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interfaccia. Per informazioni sulle interruzioni regolari e irregolari, vedere il [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazione EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
