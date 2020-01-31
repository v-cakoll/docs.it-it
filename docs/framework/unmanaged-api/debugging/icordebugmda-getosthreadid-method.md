---
title: Metodo ICorDebugMDA::GetOSThreadId
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: d9efefb26ee175fa60e7cc4516ff3f8444968f31
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793215"
---
# <a name="icordebugmdagetosthreadid-method"></a>Metodo ICorDebugMDA::GetOSThreadId
Ottiene l'identificatore del thread del sistema operativo su cui è in esecuzione l'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pOsTid`  
 out Puntatore all'identificatore del thread del sistema operativo.  
  
## <a name="remarks"></a>Note  
 Il thread del sistema operativo viene usato al posto di ICorDebugThread per consentire situazioni in cui un assistente al debug gestito viene attivato in un thread nativo o in un thread gestito che non ha ancora immesso codice gestito.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMDA](icordebugmda-interface.md)
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
