---
title: Interfaccia ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: a7a8d96548704f223f05826af79a4e227bdfab06
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379837"
---
# <a name="icordebugthread2-interface"></a>Interfaccia ICorDebugThread2
Funge da estensione logica per l'interfaccia ICorDebugThread.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetActiveFunctions](icordebugthread2-getactivefunctions-method.md)|Ottiene una matrice di istanze di COR_ACTIVE_FUNCTION che contengono dati sulle funzioni attive nei frame di un thread.|  
|[Metodo GetConnectionID](icordebugthread2-getconnectionid-method.md)|Ottiene un identificatore di connessione per l'oggetto `ICorDebugThread2` .|  
|[Metodo GetTaskID](icordebugthread2-gettaskid-method.md)|Ottiene un identificatore di attività per questo oggetto `ICorDebugThread2` .|  
|[Metodo GetVolatileOSThreadID](icordebugthread2-getvolatileosthreadid-method.md)|Ottiene l'identificatore del thread del sistema operativo per l'oggetto `ICorDebugThread2` .|  
|[Metodo InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md)|Consente a un debugger di intercettare l'eccezione corrente su un thread.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
