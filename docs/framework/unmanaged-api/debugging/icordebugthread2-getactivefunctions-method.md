---
title: Metodo ICorDebugThread2::GetActiveFunctions
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed13f78d5a1f6d54b12c86613715f4878a521bfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993967"
---
# <a name="icordebugthread2getactivefunctions-method"></a>Metodo ICorDebugThread2::GetActiveFunctions
Ottiene informazioni sulla funzione attiva in ognuno dei frame di questo thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cFunctions`  
 [in] Dimensione della matrice `pFunctions`.  
  
 `pcFunctions`  
 [out] Un puntatore al numero di oggetti restituiti nel `pFunctions` matrice. Il numero di oggetti restituito sarà uguale al numero di frame gestiti nello stack.  
  
 `pFunctions`  
 [in, out] Matrice di oggetti COR_ACTIVE_FUNCTION, ognuno dei quali contiene informazioni sulle funzioni attive nei frame di questo thread.  
  
 Il primo elemento da utilizzare per il frame foglia e così via fino alla radice dello stack.  
  
## <a name="remarks"></a>Note  
 Se `pFunctions` è null per input, `GetActiveFunctions` restituisce solo il numero di funzioni sullo stack. Vale a dire, se `pFunctions` è null per input, `GetActiveFunctions` restituisce un valore solo in `pcFunctions`.  
  
 Il `GetActiveFunctions` metodo è inteso come ottimizzazione acquisizione le stesse informazioni da una traccia dello stack frame e include solo i frame che avrebbe dovuto un oggetto ICorDebugILFrame per essi nell'analisi dello stack completo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
