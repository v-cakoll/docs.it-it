---
title: Metodo ICorDebugManagedCallback::LoadModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d133bffdf98306c17bb223dc25e84d6bf9e2ce2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a>Metodo ICorDebugManagedCallback::LoadModule
Notifica al debugger che un modulo di common language runtime (CLR) è stato caricato correttamente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stato caricato il modulo.  
  
 `pModule`  
 [in] Un puntatore a un oggetto ICorDebugModule che rappresenta il modulo CLR.  
  
## <a name="remarks"></a>Note  
 Il `LoadModule` callback fornisce un momento appropriato per esaminare i metadati per il modulo, impostare i flag del compilatore just-in-time (JIT) o di abilitare o disabilitare i callback per il modulo di caricamento delle classi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [UnloadModule (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [ICorDebugManagedCallback (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
