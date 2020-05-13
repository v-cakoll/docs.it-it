---
title: Metodo ICorDebugFrame::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205455"
---
# <a name="icordebugframecreatestepper-method"></a>Metodo ICorDebugFrame::CreateStepper
Ottiene un oggetto stepper che consente al debugger di eseguire operazioni di esecuzione dei progressi rispetto a questo ICorDebugFrame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppStepper`  
 out Puntatore all'indirizzo di un oggetto ICorDebugStepper che consente al debugger di eseguire operazioni di esecuzione dei progressi rispetto al frame corrente.  
  
## <a name="remarks"></a>Osservazioni  
 Se il frame non è attivo, l'oggetto stepper dovrà in genere tornare al frame prima del completamento del passaggio.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
