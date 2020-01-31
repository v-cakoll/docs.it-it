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
ms.openlocfilehash: f4f73b99b4cb48690a2a8611dbf5a5420adab5d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794349"
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
> Se si chiama `RemapFunction`, ad esempio chiamando [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md), verranno immediatamente Invalidate tutte le interfacce di debug correlate alla generazione di un'analisi dello stack per il thread. Queste interfacce includono [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame e ICorDebugNativeFrame.  
  
 Il metodo `RemapFunction` può essere chiamato solo nel contesto del frame corrente e solo in uno dei casi seguenti:  
  
- Dopo la ricezione di un callback [ICorDebugManagedCallback2:: FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) che non è stato ancora continuato.  
  
- Durante l'esecuzione del codice interrotto a causa di un evento [ICorDebugManagedCallback:: EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) per questo frame.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
