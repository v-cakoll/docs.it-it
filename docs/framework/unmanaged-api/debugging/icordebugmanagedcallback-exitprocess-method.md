---
title: Metodo ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 4518637eb47acf416a02c045f8ca6f8a90167277
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130784"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>Metodo ICorDebugManagedCallback::ExitProcess
Notifica al debugger che un processo è stato terminato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo.  
  
## <a name="remarks"></a>Note  
 Non è possibile continuare da un evento `ExitProcess`. Questo evento può essere generato in modo asincrono ad altri eventi mentre il processo sembra arrestarsi. Questo problema può verificarsi se il processo termina durante l'arresto, in genere a causa di una forza esterna.  
  
 Se il Common Language Runtime (CLR) sta già inviando un callback gestito, questo evento verrà posticipato fino a quando non viene restituito tale callback.  
  
 L'evento `ExitProcess` è l'unico evento di uscita/scaricamento garantito per essere chiamato all'arresto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
