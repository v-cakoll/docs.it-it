---
title: Metodo ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: f9a9038bd0d268e09d8518fa50534a9959b456de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122181"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Metodo ICorDebugDataTarget2::CreateVirtualUnwinder
Crea un nuovo agente di rimozione dello stack che avvia la rimozione da un contesto iniziale (non necessariamente la foglia di un thread).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>Parametri  
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
 `S_OK` se l'operazione riesce. Qualsiasi altro `HRESULT` indica un errore. Tutte le `HRESULT` non riuscite ricevute da mscordbi vengono considerate irreversibili e causano la restituzione `CORDBG_E_DATA_TARGET_ERROR`dei metodi [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) .  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
