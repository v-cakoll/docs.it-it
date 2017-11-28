---
title: Enumerazione CorDebugCodeInvokeKind
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCodeInvokeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d46a47c7c655a960224bb836be0ea37cd07c8038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 Questa enumerazione viene utilizzata per la [Icordebugprocess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) metodo per fornire informazioni sull'avanzamento tramite codice gestito.  
  
> [!NOTE]
>  Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
