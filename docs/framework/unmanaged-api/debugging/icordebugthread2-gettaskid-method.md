---
title: Metodo ICorDebugThread2::GetTaskID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: 841af546cc3586529fe290c69e686438f634b90d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377789"
---
# <a name="icordebugthread2gettaskid-method"></a>Metodo ICorDebugThread2::GetTaskID
Ottiene l'identificatore dell'attività in esecuzione su questo thread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pTaskId`  
 out Puntatore all'identificatore dell'attività in esecuzione sul thread rappresentato da questo oggetto ICorDebugThread2.  
  
## <a name="remarks"></a>Osservazioni  
 Un'attività può essere eseguita solo nel thread se il thread è associato a una connessione. `GetTaskID`restituisce zero in `pTaskId` se il thread non è associato a una connessione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
