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
ms.openlocfilehash: 9452f238bd84c9c185ca8e007acac563474d29df
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212061"
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
 out Puntatore a un valore booleano che è `true` se il thread specificato è stato sospeso; in caso contrario, * `pbSuspended` è `false` .  
  
## <a name="remarks"></a>Osservazioni  
 Quando il thread specificato è stato sospeso a causa dell'arresto del processo da parte del debugger, il numero di sospensione Win32 del thread specificato viene incrementato di uno. L'interfaccia utente del debugger può voler prendere in considerazione queste informazioni se Visualizza il numero di sospensione del thread del sistema operativo per l'utente.  
  
 Il `IsOSSuspended` metodo è utile solo nel contesto del debug non gestito. Durante il debug gestito, i thread vengono sospesi in modo cooperativo anziché sospesi dal sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
