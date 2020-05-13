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
ms.openlocfilehash: a74d32478bc88ee634fa5ff9b61ac2059bc8e302
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379713"
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
 out Puntatore all'indirizzo di un `ICorDebugStepper` oggetto che consente l'esecuzione di un'istruzione alla volta nel frame attivo del thread.  
  
## <a name="remarks"></a>Osservazioni  
 Il frame attivo può essere codice non gestito.  
  
 `ICorDebugStepper`È necessario utilizzare l'interfaccia per eseguire l'esecuzione dell'istruzione effettiva.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
