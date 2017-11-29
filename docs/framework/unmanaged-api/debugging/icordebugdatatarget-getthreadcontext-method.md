---
title: Metodo ICorDebugDataTarget::GetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetThreadContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 543956bb42d7477456426d7327f14b059b23d759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>Metodo ICorDebugDataTarget::GetThreadContext
Restituisce il contesto del thread corrente per il thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwThreadID`  
 [in] L'identificatore del thread il cui contesto è da recuperare. L'identificatore è definito dal sistema operativo.  
  
 `contextFlags`  
 [in] Combinazione bit per bit di flag dipendente dalla piattaforma che indicano quali parti del contesto deve essere letti.  
  
 `contextSize`  
 [in] Le dimensioni di `pContext`.  
  
 `pContext`  
 [out] Buffer in cui verrà archiviato nel contesto del thread.  
  
## <a name="remarks"></a>Note  
 Su piattaforme Windows, `pContext` deve essere un `CONTEXT` struttura (definito in Winnt. H) appropriata per il tipo di computer specificato per il [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metodo. `contextFlags`deve avere gli stessi valori di `ContextFlags` campo il `CONTEXT` struttura. Il `CONTEXT` struttura è specifico del processore, vedere il file Winnt. H per informazioni dettagliate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugDataTarget (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
