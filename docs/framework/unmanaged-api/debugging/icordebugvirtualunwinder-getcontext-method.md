---
title: Metodo ICorDebugVirtualUnwinder::GetContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d034016c7470cbf134cb142db9f98d82d0c59d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parametri  
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
 Impostare il valore iniziale del `contextBuf` argomento per il buffer del contesto restituito dalla chiamata di [ICorDebugStackWalk::](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) (metodo).  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
 Poiché l'agente di rimozione potrebbe ripristinare solo un subset dei registri, ad esempio solo quelli non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento dell'effettiva chiamata al metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
