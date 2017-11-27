---
title: Metodo ICorDebugManagedCallback::EvalComplete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6211a5f0038c6244f7732e0c0ba854aaa1e6092e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a>Metodo ICorDebugManagedCallback::EvalComplete
Notifica al debugger che una versione di valutazione è stata completata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata eseguita la valutazione.  
  
 `pThread`  
 [in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata eseguita la valutazione.  
  
 `pEval`  
 [in] Un puntatore a un oggetto ICorDebugEval che rappresenta il codice che ha eseguito la valutazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugManagedCallback (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
