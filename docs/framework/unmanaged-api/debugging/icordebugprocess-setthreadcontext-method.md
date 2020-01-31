---
title: Metodo ICorDebugProcess::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: 66d544bbc0511ea76565376c8f10294f1758026b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792568"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>Metodo ICorDebugProcess::SetThreadContext
Imposta il contesto per il thread specificato in questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadID`  
 in ID del thread per il quale impostare il contesto.  
  
 `contextSize`  
 [in] Dimensione della matrice `context`.  
  
 `context`  
 in Matrice di byte che descrivono il contesto del thread.  
  
 Il contesto specifica l'architettura del processore in cui è in esecuzione il thread.  
  
## <a name="remarks"></a>Note  
 Il debugger deve chiamare questo metodo anziché la funzione Win32 `SetThreadContext`, perché il thread può effettivamente trovarsi in uno stato di "Hijack", in cui il contesto è stato modificato temporaneamente. Questo metodo deve essere utilizzato solo quando un thread è in codice nativo. Usare [ICorDebugRegisterSet](icordebugregisterset-interface.md) per i thread nel codice gestito. Non è mai necessario modificare il contesto di un thread durante un evento di debug fuori banda (OOB).  
  
 I dati passati devono essere una struttura di contesto per la piattaforma corrente.  
  
 Questo metodo può danneggiare il runtime se usato in modo errato.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
