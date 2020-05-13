---
title: Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: d2fc59621cbb6752830c7a8392ce4e0c476ef9e7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210059"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
Notifica al debugger che l'esecuzione del codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene la funzione modificata.  
  
 `pThread`  
 in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato rilevato il punto di interruzione del mapping.  
  
 `pOldFunction`  
 in Puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione nel thread.  
  
 `pNewFunction`  
 in Puntatore a un oggetto ICorDebugFunction che rappresenta la versione più recente della funzione.  
  
 `oldILOffset`  
 in Offset MSIL (Microsoft Intermediate Language) del puntatore all'istruzione nella versione precedente della funzione.  
  
## <a name="remarks"></a>Osservazioni  
 Questo callback offre al debugger un'opportunità per modificare il mapping del puntatore all'istruzione alla posizione corretta nella nuova versione della funzione specificata chiamando il metodo [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) . Se il debugger non chiama `RemapFunction` prima di chiamare il metodo [ICorDebugController:: continue](icordebugcontroller-continue-method.md) , il runtime continuerà a eseguire il codice precedente e genererà un altro `FunctionRemapOpportunity` callback al successivo punto di sequenza.  
  
 Questo callback verrà richiamato per ogni frame che esegue una versione precedente della funzione specificata fino a quando il debugger non restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
