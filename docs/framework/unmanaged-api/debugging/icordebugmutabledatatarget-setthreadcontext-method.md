---
title: Metodo ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: a6df6bf030ad339f5d02b95cd191b30db60aa167
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210150"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>Metodo ICorDebugMutableDataTarget::SetThreadContext
Imposta il contesto (valori del registro) per un thread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwThreadID`  
 [in] Identificatore del thread definito dal sistema operativo.  
  
 `contextSize`  
 [in] Dimensioni del buffer `pContext` da scrivere.  
  
 `pContext`  
 [in] Puntatore ai byte da scrivere.  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo `SetThreadContext` aggiorna il contesto corrente per il thread specificato dall'argomento `dwThreadID` definito dal sistema operativo. Il formato del record di contesto è determinato dalla piattaforma indicata dal metodo [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) . In Windows si tratta di una struttura di [contesto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
