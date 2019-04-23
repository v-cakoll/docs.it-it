---
title: Metodo ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8b3fd9940bd11c3d026b46247e0657c82b18099
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120003"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>Metodo ICorDebugMutableDataTarget::SetThreadContext
Imposta il contesto (valori del registro) per un thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
## <a name="remarks"></a>Note  
 Il metodo `SetThreadContext` aggiorna il contesto corrente per il thread specificato dall'argomento `dwThreadID` definito dal sistema operativo. Il formato del record di contesto è determinato dalla piattaforma indicata per la [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) (metodo). In Windows, si tratta di un [contesto](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) struttura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMutableDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
