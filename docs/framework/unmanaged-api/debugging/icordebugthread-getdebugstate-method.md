---
title: Metodo ICorDebugThread::GetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95d9696e29bc1b460c94d7f4d8afd3de82653333
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419630"
---
# <a name="icordebugthreadgetdebugstate-method"></a>Metodo ICorDebugThread::GetDebugState
Ottiene lo stato di debug corrente di questo oggetto ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pState`  
 [out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugThreadState che descrive lo stato di debug corrente di questo thread.  
  
## <a name="remarks"></a>Note  
 Se il processo è inattivo, `pState` rappresenta lo stato di debug che avrebbe questo thread se il processo continua, non l'effettivo stato corrente di questo thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
