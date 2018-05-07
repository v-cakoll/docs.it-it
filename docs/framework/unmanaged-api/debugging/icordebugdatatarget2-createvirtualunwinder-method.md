---
title: Metodo ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92dd0a4ad8128f7ce300ca5da1e5022b944d91e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Metodo ICorDebugDataTarget2::CreateVirtualUnwinder
Crea un nuovo agente di rimozione dello stack che avvia la rimozione da un contesto iniziale (non necessariamente la foglia di un thread).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
#### <a name="parameters"></a>Parametri  
 nativeThreadID  
 [in] L'ID thread nativo del thread di cui rimuovere lo stack.  
  
 contextFlags  
 [in] Flag che specificano le parti del contesto definite in `initialContext`.  
  
 cbContext  
 [in] Le dimensioni di `initialContext`.  
  
 initialContext  
 [in] I dati nel contesto.  
  
 ppUnwinder  
 [out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugVirtualUnwinder.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se l'operazione riesce. Qualsiasi altro `HRESULT` indica un errore. Qualsiasi errore `HRESULT` ricevuto da mscordbi viene considerato irreversibile e causa [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) metodi per restituire `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
