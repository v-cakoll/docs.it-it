---
title: Metodo ICorDebugILFrame2::RemapFunction
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
ms.openlocfilehash: 152cdb13a9f517a7a9c29c04a056661bb2edb45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090448"
---
# <a name="icordebugilframe2remapfunction-method"></a>Metodo ICorDebugILFrame2::RemapFunction
Consente di rimappare una funzione modificata specificando il nuovo offset MSIL (Microsoft Intermediate Language)  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `newILOffset`  
 in Nuovo offset MSIL del stack frame in corrispondenza del quale deve essere inserito il puntatore all'istruzione. Questo valore deve essere un punto di sequenza.  
  
 È responsabilità del chiamante garantire la validità di questo valore. Ad esempio, l'offset MSIL non è valido se non è compreso nei limiti della funzione.  
  
## <a name="remarks"></a>Note  
 Quando la funzione di un frame è stata modificata, il debugger può chiamare il metodo `RemapFunction` per scambiare la versione più recente della funzione del frame, in modo che possa essere eseguita. L'esecuzione del codice inizierà in corrispondenza dell'offset MSIL specificato.  
  
> [!NOTE]
> Se si chiama `RemapFunction`, ad esempio chiamando [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), verranno immediatamente Invalidate tutte le interfacce di debug correlate alla generazione di un'analisi dello stack per il thread. Queste interfacce includono [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame e ICorDebugNativeFrame.  
  
 Il metodo `RemapFunction` può essere chiamato solo nel contesto del frame corrente e solo in uno dei casi seguenti:  
  
- Dopo la ricezione di un callback [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) che non è stato ancora continuato.  
  
- Durante l'esecuzione del codice interrotto a causa di un evento [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) per questo frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
