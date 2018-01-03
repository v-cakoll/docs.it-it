---
title: Metodo ICorDebugDataTarget2::CreateVirtualUnwinder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bffbf95fc38cba6f311e0641b35e2696bd34099
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
