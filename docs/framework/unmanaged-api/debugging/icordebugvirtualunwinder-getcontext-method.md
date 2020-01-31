---
title: Metodo ICorDebugVirtualUnwinder::GetContext
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: ff5e5bdd66ec44a0931b51212f07485718507576
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790837"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a>Metodo ICorDebugVirtualUnwinder::GetContext
Ottiene il contesto corrente di questo agente di rimozione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 Impostare il valore iniziale dell'argomento `contextBuf` sul buffer del contesto restituito chiamando il metodo [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) .  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
 Poiché l'agente di rimozione potrebbe ripristinare solo un subset dei registri, ad esempio solo quelli non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento dell'effettiva chiamata al metodo.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
