---
title: Metodo ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133587"
---
# <a name="icordebugthreadcreatestepper-method"></a>Metodo ICorDebugThread::CreateStepper
Crea un oggetto ICorDebugStepper che consente l'esecuzione di un'istruzione alla volta nel frame attivo di ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppStepper`  
 out Puntatore all'indirizzo di un `ICorDebugStepper` oggetto che consente di scorrere il frame attivo del thread.  
  
## <a name="remarks"></a>Note  
 Il frame attivo può essere codice non gestito.  
  
 È necessario utilizzare l'interfaccia `ICorDebugStepper` per eseguire l'esecuzione dell'istruzione effettiva.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
