---
title: Metodo ICorDebugMutableDataTarget::ContinueStatusChanged
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d2560aa484c6965047b2fdaf2c539b8ab675bc8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207703"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>Metodo ICorDebugMutableDataTarget::ContinueStatusChanged
Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwThreadId`  
 Identificatore del thread definito dal sistema operativo.  
  
 `continueStatus`  
 Valore [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che rappresenta il nuovo stato di continuazione richiesto.  
  
## <a name="remarks"></a>Note  
 Il debugger chiama il metodo `ContinueStatusChanged` quando chiama un metodo ICorDebug che richiede di gestire l'evento di debug corrente in modo potenzialmente diverso da quello in cui verrebbe gestito di solito. Se ad esempio è presente un'eccezione in sospeso e il debugger richiede un'operazione che annullerebbe l'eccezione (ad esempio, [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o `FuncEval`), questa API viene usata per richiedere l'annullamento dell'eccezione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugMutableDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
