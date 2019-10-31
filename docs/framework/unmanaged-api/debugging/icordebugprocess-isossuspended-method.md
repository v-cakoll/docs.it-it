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
ms.openlocfilehash: 21da69d4bff0f17eb607dda45fb7dbafea8c59f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128763"
---
# <a name="icordebugprocessisossuspended-method"></a>Metodo ICorDebugProcess::IsOSSuspended
Ottiene un valore che indica se il thread specificato è stato sospeso a causa dell'arresto del processo da parte del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadID`  
 in ID del thread in questione.  
  
 `pbSuspended`  
 out Puntatore a un valore booleano che viene `true` se il thread specificato è stato sospeso; in caso contrario, *`pbSuspended` è `false`.  
  
## <a name="remarks"></a>Note  
 Quando il thread specificato è stato sospeso a causa dell'arresto del processo da parte del debugger, il numero di sospensione Win32 del thread specificato viene incrementato di uno. L'interfaccia utente del debugger può voler prendere in considerazione queste informazioni se Visualizza il numero di sospensione del thread del sistema operativo per l'utente.  
  
 Il metodo `IsOSSuspended` ha senso solo nel contesto del debug non gestito. Durante il debug gestito, i thread vengono sospesi in modo cooperativo anziché sospesi dal sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
