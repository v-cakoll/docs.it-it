---
title: Enumerazione EClrFailure
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef4e12015adc3d6e67ad9c8ba8b152cd775b85e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="eclrfailure-enumeration"></a>Enumerazione EClrFailure
Descrive il set di errori per il quale un host può impostare le azioni dei criteri.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Si è verificato un errore durante il tentativo di assegnare una risorsa (ad esempio, un thread, un blocco di memoria o un blocco) in un'area critica del codice.|  
|`FAIL_CriticalResource`|Si è verificato un errore durante il tentativo di assegnare una risorsa (ad esempio, un thread, un blocco di memoria o un blocco) in un'area critica del codice.|  
|`FAIL_FatalRuntime`|Common language runtime (CLR) non è più in grado di eseguire codice gestito nel processo. Da questo momento, le chiamate alle funzioni hosting restituiscono un valore HRESULT di HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Un thread non è riuscito a rilasciare un blocco all'uscita da un <xref:System.AppDomain> oggetto. L'host non è possibile impostare questo errore per causare l'interruzione di un thread.|  
|`FAIL_StackOverflow`|Si è verificato un overflow dello stack.|  
|`FAIL_AccessViolation`|È stato effettuato un tentativo di leggere o scrivere memoria protetta. Non supportato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].|  
|`FAIL_CodeContract`|Si è verificato un errore di contratto di codice. Vedere [contratti di codice](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Note  
 Vedere il [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metodo per un elenco di [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori l'host può utilizzare per specificare le azioni dei criteri per le condizioni di errore. Per ulteriori informazioni sulle aree non critiche di codice, vedere [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Metodo SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
