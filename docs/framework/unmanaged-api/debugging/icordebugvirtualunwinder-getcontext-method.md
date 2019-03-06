---
title: Metodo ICorDebugVirtualUnwinder::GetContext
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a554efc89c1242537bec7de074220cbec95ecdd2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481129"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a>Metodo ICorDebugVirtualUnwinder::GetContext
Ottiene il contesto corrente di questo agente di rimozione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `contextFlags`  
 [in] Flag che specificano le parti del contesto da restituire (definite in WinNT.h).  
  
 `cbContextBuf`  
 [in] Numero di byte in `contextBuf`.  
  
 `contextSize`  
 [out] Puntatore al numero di byte effettivamente scritti in `contextBuf`.  
  
 `contextBuf`  
 [out] Matrice di byte che contiene il contesto corrente di questo agente di rimozione.  
  
## <a name="return-value"></a>Valore restituito  
 Qualsiasi valore HRESULT con errori ricevuto da mscordbi viene considerato irreversibile e causa la restituzione di `CORDBG_E_DATA_TARGET_ERROR` da parte delle API ICorDebug.  
  
## <a name="remarks"></a>Note  
 Si imposta il valore iniziale del `contextBuf` argomento per il buffer del contesto restituito dalla chiamata di [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) (metodo).  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
 Poiché l'agente di rimozione potrebbe ripristinare solo un subset dei registri, ad esempio solo quelli non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento dell'effettiva chiamata al metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
