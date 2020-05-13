---
title: Metodo ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 56dc5f87b32b3aaa0bfbb69541d5a01ae26606ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213234"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>Metodo ICorDebugFunction2::GetJMCStatus
Ottiene un valore che indica se la funzione rappresentata da questo oggetto ICorDebugFunction2 è contrassegnata come codice utente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbIsJustMyCode`  
 out Puntatore a un valore booleano `true` , se questa funzione è contrassegnata come codice utente; in caso contrario, il valore è `false` .  
  
## <a name="remarks"></a>Osservazioni  
 Se la funzione rappresentata da questo oggetto `ICorDebugFunction2` non può essere `pbIsJustMyCode` sottoposta a debug, sarà sempre `false` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
