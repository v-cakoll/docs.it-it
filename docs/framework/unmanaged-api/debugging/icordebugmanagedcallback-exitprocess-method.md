---
title: Metodo ICorDebugManagedCallback::ExitProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7be74520fff65b113f54d82305a84dd183286876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>Metodo ICorDebugManagedCallback::ExitProcess
Notifica al debugger che un processo è terminato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pProcess`  
 [in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo.  
  
## <a name="remarks"></a>Note  
 È possibile proseguire da un `ExitProcess` evento. Questo evento potrebbe essere generato in modo asincrono e gli altri eventi mentre il processo da arrestare. Ciò può verificarsi se il processo viene interrotto mentre arrestato, in genere a causa di alcune forza esterna.  
  
 Se common language runtime (CLR) sta già inviando un callback gestito, questo evento verrà ritardato fino a dopo che ha restituito il callback.  
  
 Il `ExitProcess` evento è l'unico evento di uscita o scaricamento che viene chiamato in fase di arresto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
