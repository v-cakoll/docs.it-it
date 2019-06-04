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
ms.openlocfilehash: cb19f950122f7b0db66830e9ed5dff44ccd370c2
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490432"
---
# <a name="eclrfailure-enumeration"></a>Enumerazione EClrFailure
Descrive il set di errori per il quale l'host può impostare le azioni dei criteri.  
  
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Si è verificato un errore durante il tentativo di allocare una risorsa (ad esempio, un thread, un blocco di memoria o un blocco) in un'area critica del codice.|  
|`FAIL_CriticalResource`|Si è verificato un errore durante il tentativo di allocare una risorsa (ad esempio, un thread, un blocco di memoria o un blocco) in un'area critica del codice.|  
|`FAIL_FatalRuntime`|Common language runtime (CLR) non è più in grado di eseguire codice gestito nel processo. Da questo momento, le chiamate a qualsiasi host funzioni restituiscono un valore HRESULT di HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Un thread non è riuscito a rilasciare un blocco all'uscita da un <xref:System.AppDomain> oggetto. L'host non è possibile impostare questo tentativo provoca l'interruzione di un thread.|  
|`FAIL_StackOverflow`|Si è verificato un overflow dello stack.|  
|`FAIL_AccessViolation`|È stato effettuato un tentativo di leggere o scrivere nella memoria protetta. Non è supportato in .NET Framework 4.|  
|`FAIL_CodeContract`|Si è verificato un errore di contratto di codice. Visualizzare [contratti di codice](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Note  
 Vedere le [SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metodo per un elenco delle [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori host possono essere utilizzati per specificare le azioni dei criteri per le condizioni di errore. Per altre informazioni sulle aree critiche e non critici del codice, vedere [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Metodo SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [Interfaccia IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
