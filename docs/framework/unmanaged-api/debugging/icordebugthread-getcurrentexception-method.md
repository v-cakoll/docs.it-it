---
title: Metodo ICorDebugThread::GetCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4baa4eb4da48b923ab0137ca25d9d819c94e33d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487343"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>Metodo ICorDebugThread::GetCurrentException
Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppExceptionObject`  
 [out] Un puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta l'eccezione generata dal codice gestito.  
  
## <a name="remarks"></a>Note  
 L'oggetto eccezione sarà disponibile dal momento in cui viene generata l'eccezione fino alla fine del `catch` blocco. Una valutazione della funzione, che viene eseguita dai metodi ICorDebugEval, cancellerà l'oggetto eccezione nel programma di installazione e ripristinarlo quindi sul completamento.  
  
 Le eccezioni possono essere annidate (ad esempio, se viene generata un'eccezione in un filtro o in una funzione di valutazione), potrebbero essere presenti più eccezioni in sospeso in un unico thread. `GetCurrentException` Restituisce l'eccezione più recente.  
  
 L'oggetto eccezione e il tipo può cambiare per tutta la durata dell'eccezione. Ad esempio, dopo che viene generata un'eccezione di tipo x, common language runtime (CLR) può eseguire memoria insufficiente e alzato di livello un'eccezione di memoria insufficiente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
