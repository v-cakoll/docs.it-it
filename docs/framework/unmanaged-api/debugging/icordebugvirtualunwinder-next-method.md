---
title: Metodo ICorDebugVirtualUnwinder::Next
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: 55f10a6148f0b11cf74492afe947d5921a1d1458
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396422"
---
# <a name="icordebugvirtualunwindernext-method"></a>Metodo ICorDebugVirtualUnwinder::Next
Avanza fino al contesto del chiamante.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a>Parametri  
 No.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la rimozione è stata eseguita correttamente o `CORDBG_S_AT_END_OF_STACK` se la rimozione non riesce perché non vi sono più frame.  
  
 Se viene restituito un HRESULT, le API ICorDebug restituiranno `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Commenti  
 Il percorso di chiamate nello stack deve garantire un progresso in avanti, in modo che un'eventuale chiamata a `Next` restituisca un errore HRESULT o `CORDBG_S_AT_END_OF_STACK`. La restituzione illimitata `S_OK` può causare un ciclo infinito.  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
