---
title: Enumerazione EClrUnhandledException
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 63b07dda2293d3e05bd3c8fcdc45f20a498ea54c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616307"
---
# <a name="eclrunhandledexception-enumeration"></a>Enumerazione EClrUnhandledException
Descrive le opzioni disponibili per la gestione delle eccezioni non gestite nel codice utente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|Specifica che si verifica il comportamento predefinito. Il processo è stato eliminato.|  
|`eHostDeterminedPolicy`|Specifica che il Common Language Runtime (CLR) ignora le eccezioni non gestite e consente all'host di determinare eventuali ulteriori azioni.|  
  
## <a name="remarks"></a>Osservazioni  
 Per specificare che CLR si comporti come le versioni precedenti, utilizzare il `eHostDeterminedPolicy` membro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrFailure](eclrfailure-enumeration.md)
- [Enumerazione EClrOperation](eclroperation-enumeration.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Metodo SetUnhandledExceptionPolicy](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [Interfaccia IHostPolicyManager](ihostpolicymanager-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
