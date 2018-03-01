---
title: Metodo ICorDebugThread::GetCurrentException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c18e2dfa68d425e5ec23d4573428018bc971f8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetcurrentexception-method"></a>Metodo ICorDebugThread::GetCurrentException
Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppExceptionObject`  
 [out] Un puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta l'eccezione generata dal codice gestito.  
  
## <a name="remarks"></a>Note  
 L'oggetto eccezione esisterà dal momento in cui viene generata l'eccezione fino alla fine del `catch` blocco. Una valutazione della funzione, che viene eseguita dai metodi ICorDebugEval, cancellerà l'oggetto eccezione della configurazione e ripristinarlo al completamento.  
  
 Le eccezioni possono essere annidate (ad esempio, se viene generata un'eccezione in un filtro o in una valutazione della funzione), pertanto potrebbero essere presenti più eccezioni in attesa su un thread singolo. `GetCurrentException`Restituisce l'eccezione più recente.  
  
 L'oggetto eccezione e il tipo può variare per tutta la durata dell'eccezione. Ad esempio, dopo che viene generata un'eccezione di tipo x, common language runtime (CLR) può memoria insufficiente e convertirlo in un'eccezione di memoria insufficiente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
