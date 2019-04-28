---
title: Metodo ICorDebugProcess::IsOSSuspended
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039dc0d9befb038e643abc4e2524c133234f460b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775563"
---
# <a name="icordebugprocessisossuspended-method"></a>Metodo ICorDebugProcess::IsOSSuspended
Ottiene un valore che indica se il thread specificato è stata sospesa in seguito il debugger di interruzione del processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadID`  
 [in] L'ID del thread in questione.  
  
 `pbSuspended`  
 [out] Un puntatore a un valore booleano che è `true` se il thread specificato è stata sospesa; in caso contrario *`pbSuspended` è `false`.  
  
## <a name="remarks"></a>Note  
 Quando il thread specificato è stata sospesa in seguito il debugger di interruzione del processo, un conteggio di sospensione Win32 del thread specificato viene incrementato di uno. L'interfaccia utente del debugger (UI) potrebbe voler sfruttare queste informazioni in considerazione se viene visualizzato il sistema operativo (OS) sospendere conteggio dei thread per l'utente.  
  
 Il `IsOSSuspended` metodo senso solo nel contesto di debug non gestito. Durante il debug gestito, i thread sono in modo cooperativo sospeso anziché sospeso del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
