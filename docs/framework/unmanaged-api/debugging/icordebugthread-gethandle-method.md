---
title: Metodo ICorDebugThread::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 33219d9a67379244e23da49c13617a4c4a2fa66d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133457"
---
# <a name="icordebugthreadgethandle-method"></a>Metodo ICorDebugThread::GetHandle
Ottiene l'handle corrente per la parte attiva di ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phThreadHandle`  
 out Puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.  
  
## <a name="remarks"></a>Note  
 L'handle può cambiare durante l'esecuzione del processo e può essere diverso per le diverse parti del thread.  
  
 Questo handle è di proprietà dell'API di debug. Il debugger dovrebbe duplicarlo prima di usarlo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
