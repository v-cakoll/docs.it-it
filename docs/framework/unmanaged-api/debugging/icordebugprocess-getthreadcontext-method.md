---
title: Metodo ICorDebugProcess::GetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9cb2b0be2954c041b364f9c85c40570a9f04421f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgetthreadcontext-method"></a>Metodo ICorDebugProcess::GetThreadContext
Ottiene il contesto per il thread specificato in questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `threadID`  
 [in] L'ID del thread per il quale recuperare il contesto.  
  
 `contextSize`  
 [in] Dimensione della matrice `context`.  
  
 `context`  
 [in, out] Matrice di byte che descrivono il contesto del thread.  
  
 Il contesto specifica l'architettura del processore in cui il thread è in esecuzione.  
  
## <a name="remarks"></a>Note  
 Il debugger deve chiamare questo metodo anziché Win32 `GetThreadContext` metodo, perché il thread potrebbe essere in uno stato "fraudolente", in cui è stato temporaneamente modificato il relativo contesto. Questo metodo deve essere utilizzato solo quando un thread in codice nativo. Utilizzare [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) per i thread nel codice gestito.  
  
 I dati restituiti sono una struttura di contesto per la piattaforma corrente. Come con Win32 `GetThreadContext` (metodo), il chiamante deve inizializzare il `context` parametro prima di chiamare questo metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
