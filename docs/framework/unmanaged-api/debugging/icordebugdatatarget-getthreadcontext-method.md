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
ms.openlocfilehash: 79708aa5a2abcb8d7465f82a8beb918484c193b9
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976551"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>Metodo ICorDebugDataTarget::GetThreadContext
Restituisce il contesto del thread corrente per il thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwThreadID`  
 in Identificatore del thread di cui è necessario recuperare il contesto. L'identificatore viene definito dal sistema operativo.  
  
 `contextFlags`  
 in Combinazione bit per bit di flag dipendenti dalla piattaforma che indicano quali parti del contesto devono essere lette.  
  
 `contextSize`  
 [in] Le dimensioni di `pContext`.  
  
 `pContext`  
 out Buffer in cui verrà archiviato il contesto del thread.  
  
## <a name="remarks"></a>Osservazioni  
 Nelle piattaforme Windows, `pContext` deve essere una `CONTEXT` struttura (definita in Winnt. h) appropriata per il tipo di computer specificato dal metodo [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) . `contextFlags`deve avere gli stessi valori del `ContextFlags` campo della `CONTEXT` struttura. La `CONTEXT` struttura è specifica del processore. per informazioni dettagliate, vedere il file WinNT. h.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
