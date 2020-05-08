---
title: Metodo ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 7a479fba9bbcf28c60474fffc6219af23e62c251
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976499"
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
 `S_OK` se l'operazione riesce. Qualsiasi altro `HRESULT` indica un errore. Qualsiasi errore `HRESULT` ricevuto da mscordbi viene considerato irreversibile e causa [ICorDebug](icordebug-interface.md) la restituzione `CORDBG_E_DATA_TARGET_ERROR`dei metodi ICorDebug.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
