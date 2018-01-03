---
title: Metodo ICorDebugProcess::SetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a>Metodo ICorDebugProcess::SetThreadContext
Imposta il contesto per il thread specificato in questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `threadID`  
 [in] L'ID del thread per il quale impostare il contesto.  
  
 `contextSize`  
 [in] Dimensione della matrice `context`.  
  
 `context`  
 [in] Matrice di byte che descrivono il contesto del thread.  
  
 Il contesto specifica l'architettura del processore in cui il thread è in esecuzione.  
  
## <a name="remarks"></a>Note  
 Il debugger deve chiamare questo metodo anziché Win32 `SetThreadContext` funzionare, perché il thread potrebbe essere in uno stato "fraudolente", in cui è stato temporaneamente modificato il relativo contesto. Questo metodo deve essere utilizzato solo quando un thread in codice nativo. Utilizzare [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) per i thread nel codice gestito. Non è necessario modificare il contesto di un thread durante un evento di debug fuori banda (OOB).  
  
 I dati passati devono essere una struttura di contesto per la piattaforma corrente.  
  
 Questo metodo può danneggiare il runtime, se utilizzato in modo non corretto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
