---
title: Metodo ICorDebugThread::GetID
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52962ea7d2cf3dd1822b1a36cc6cfcb56bc427f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadgetid-method"></a>Metodo ICorDebugThread::GetID
Ottiene l'identificatore del sistema operativo corrente della parte attiva del ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pdwThreadId`  
 [out] L'identificatore del thread.  
  
## <a name="remarks"></a>Note  
 L'identificatore del sistema operativo può essere modificato durante l'esecuzione di un processo e può essere un valore diverso per le diverse parti del thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
