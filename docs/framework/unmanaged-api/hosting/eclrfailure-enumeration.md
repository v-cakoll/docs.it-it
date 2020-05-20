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
ms.openlocfilehash: e07210203d8a8010890eeb511ff1c08821bfc4a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616333"
---
# <a name="eclrfailure-enumeration"></a>Enumerazione EClrFailure
Descrive il set di errori per i quali un host può impostare le azioni dei criteri.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Membro|Description|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Si è verificato un errore durante il tentativo di allocare una risorsa, ad esempio un thread, un blocco di memoria o un blocco, in un'area di codice non critica.|  
|`FAIL_CriticalResource`|Si è verificato un errore durante il tentativo di allocare una risorsa, ad esempio un thread, un blocco di memoria o un blocco, in un'area critica del codice.|  
|`FAIL_FatalRuntime`|Il Common Language Runtime (CLR) non è più in grado di eseguire il codice gestito nel processo. In questo caso, le chiamate a qualsiasi funzione di hosting restituiscono un valore HRESULT pari a HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Un thread non è riuscito a rilasciare un blocco in seguito alla restituzione da un <xref:System.AppDomain> oggetto. L'host non è in grado di impostare questo errore in modo da causare l'interruzione di un thread.|  
|`FAIL_StackOverflow`|Si è verificato un overflow dello stack.|  
|`FAIL_AccessViolation`|È stato effettuato un tentativo di lettura o scrittura della memoria protetta. Non supportato in .NET Framework 4.|  
|`FAIL_CodeContract`|Si è verificato un errore del contratto di codice. Vedere [contratti di codice](../../debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Osservazioni  
 Vedere il metodo [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) per un elenco di valori [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) che l'host può usare per specificare le azioni dei criteri per le condizioni di errore. Per ulteriori informazioni sulle aree di codice critiche e non critiche, vedere [EClrOperation](eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Metodo SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md)
- [Interfaccia IHostPolicyManager](ihostpolicymanager-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
