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
ms.openlocfilehash: e064a7db131a671adc4d0b6df522f3456e3a31d5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377162"
---
# <a name="icordebugthread2getactivefunctions-method"></a>Metodo ICorDebugThread2::GetActiveFunctions
Ottiene informazioni sulla funzione attiva in ogni frame del thread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 out Puntatore al numero di oggetti restituiti nella `pFunctions` matrice. Il numero di oggetti restituiti sarà uguale al numero di frame gestiti nello stack.  
  
 `pFunctions`  
 [in, out] Matrice di oggetti COR_ACTIVE_FUNCTION, ognuno dei quali contiene informazioni sulle funzioni attive nei frame del thread.  
  
 Il primo elemento verrà usato per il frame foglia e così via tornando alla radice dello stack.  
  
## <a name="remarks"></a>Osservazioni  
 Se `pFunctions` è null per l'input, `GetActiveFunctions` restituisce solo il numero di funzioni presenti nello stack. Ovvero, se `pFunctions` è null per l'input, `GetActiveFunctions` restituisce un valore solo in `pcFunctions` .  
  
 Il `GetActiveFunctions` metodo è concepito come ottimizzazione per ottenere le stesse informazioni dai frame in una traccia dello stack e include solo i frame per i quali sarebbe stato disponibile un oggetto ICorDebugILFrame nell'analisi dello stack completa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
