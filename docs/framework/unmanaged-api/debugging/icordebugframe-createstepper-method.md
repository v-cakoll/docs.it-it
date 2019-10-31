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
ms.openlocfilehash: 6ea2b24d37f56a5cb9e6b3dea0d666c8acc719dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091036"
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
  
## <a name="remarks"></a>Note  
 Se il frame non è attivo, l'oggetto stepper dovrà in genere tornare al frame prima del completamento del passaggio.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
