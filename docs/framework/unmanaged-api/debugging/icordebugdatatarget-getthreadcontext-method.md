---
title: Metodo ICorDebugDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab2fbf6bb08a33158ea450f0f19eca50e280d8c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412880"
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
 Su piattaforme Windows, `pContext` deve essere un `CONTEXT` struttura (definito in Winnt. H) appropriata per il tipo di computer specificato per il [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metodo. `contextFlags` deve avere gli stessi valori di `ContextFlags` campo il `CONTEXT` struttura. Il `CONTEXT` struttura è specifico del processore, vedere il file Winnt. H per informazioni dettagliate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
