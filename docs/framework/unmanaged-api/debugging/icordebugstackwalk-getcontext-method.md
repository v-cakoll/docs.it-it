---
title: Metodo ICorDebugStackWalk::GetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 9953d0f3e1a4d4cd935918f0e5721e474453ca7d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791902"
---
# <a name="icordebugstackwalkgetcontext-method"></a>Metodo ICorDebugStackWalk::GetContext
Restituisce il contesto per il frame corrente nell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `contextFlags`  
 in Flag che indicano il contenuto richiesto del buffer del contesto (definito in WinNT. h).  
  
 `contextBufSize`  
 in Dimensione allocata del buffer del contesto.  
  
 `contextSize`  
 out Dimensioni effettive del contesto. Questo valore deve essere minore o uguale alla dimensione del buffer del contesto.  
  
 `contextBuf`  
 out Buffer del contesto.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il contesto per il frame corrente è stato restituito correttamente.|  
|E_FAIL|Non è stato possibile restituire il contesto.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|Il buffer del contesto è troppo piccolo.|  
|CORDBG_E_PAST_END_OF_STACK|Il puntatore al frame è già alla fine dello stack. non è pertanto possibile accedere a nessun frame aggiuntivo.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Poiché la rimozione ripristina solo un subset dei registri, ad esempio i registri non volatili, il contesto potrebbe non corrispondere esattamente allo stato del registro al momento della chiamata.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
