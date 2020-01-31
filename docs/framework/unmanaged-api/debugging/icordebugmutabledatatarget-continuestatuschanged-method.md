---
title: Metodo ICorDebugMutableDataTarget::ContinueStatusChanged
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: c918bb60fba5bc1ec3f0f7c58b103d05a3c7ddfd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792868"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>Metodo ICorDebugMutableDataTarget::ContinueStatusChanged
Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwThreadId`  
 Identificatore del thread definito dal sistema operativo.  
  
 `continueStatus`  
 Valore [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che rappresenta il nuovo stato di continuazione richiesto.  
  
## <a name="remarks"></a>Note  
 Il debugger chiama il metodo `ContinueStatusChanged` quando chiama un metodo ICorDebug che richiede di gestire l'evento di debug corrente in modo potenzialmente diverso da quello in cui verrebbe gestito di solito. Se ad esempio è presente un'eccezione in sospeso e il debugger richiede un'operazione che annullerebbe l'eccezione (ad esempio, [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) o `FuncEval`), questa API viene usata per richiedere l'annullamento dell'eccezione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
