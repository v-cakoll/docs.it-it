---
title: Metodo ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05f0c0d23b4885f2d6fd351fdf845a25c899228e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>Metodo ICorDebugMutableDataTarget::SetThreadContext
Imposta il contesto (valori del registro) per un thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwThreadID`  
 [in] Identificatore del thread definito dal sistema operativo.  
  
 `contextSize`  
 [in] Dimensioni del buffer `pContext` da scrivere.  
  
 `pContext`  
 [in] Puntatore ai byte da scrivere.  
  
## <a name="remarks"></a>Note  
 Il metodo `SetThreadContext` aggiorna il contesto corrente per il thread specificato dall'argomento `dwThreadID` definito dal sistema operativo. Il formato del record di contesto è determinato dalla piattaforma indicata dal [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metodo. In Windows, si tratta di un [contesto](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) struttura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugMutableDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
