---
title: Enumerazione CorDebugCodeInvokeKind
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d712a46a8ddb79846e56077e9ed6283ea4d40ba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523883"
---
# <a name="cordebugcodeinvokekind-enumeration"></a>Enumerazione CorDebugCodeInvokeKind
Descrive in che modo una funzione esportata richiama il codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|Se il codice gestito viene richiamato con questo metodo, in un secondo momento dovrà essere individuato mediante eventi espliciti o punti di interruzione.<br /><br /> --oppure--<br /><br /> È possibile che alcune parti di codice gestito chiamate dal metodo vadano perdute perché non esiste un modo semplice per arrestarlo.<br /><br /> --oppure--<br /><br /> Il metodo può non richiamare il codice gestito.|  
|`CODE_INVOKE_KIND_RETURN`|Il metodo richiama il codice gestito mediante un'istruzione di restituzione. Nel codice gestito successivo viene eseguita l'uscita.|  
|`CODE_INVOKE_KIND_TAILCALL`|Questo metodo richiama il codice gestito mediante una chiamata tail. L'esecuzione passo-passo e l'esecuzione di istruzioni per tutte le istruzioni della chiamata vengono completate nel codice gestito.|  
  
## <a name="remarks"></a>Note  
 Questa enumerazione viene utilizzata per la [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) metodo per fornire informazioni sull'esecuzione di istruzioni tramite codice gestito.  
  
> [!NOTE]
>  Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
