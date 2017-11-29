---
title: Metodo ICorDebugThread2::GetActiveFunctions
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetActiveFunctions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1f7f416a5441b788394e93a98d274d02fa2ec2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
  
#### <a name="parameters"></a>Parametri  
 `cFunctions`  
 [in] Dimensione della matrice `pFunctions`.  
  
 `pcFunctions`  
 [out] Un puntatore al numero di oggetti restituiti nel `pFunctions` matrice. Il numero di oggetti restituito sarà uguale al numero di frame gestiti nello stack.  
  
 `pFunctions`  
 [in, out] Matrice di oggetti COR_ACTIVE_FUNCTION, ognuno dei quali contiene informazioni sulle funzioni attive nei frame di questo thread.  
  
 Il primo elemento verrà utilizzato per il frame foglia e così via fino alla radice dello stack.  
  
## <a name="remarks"></a>Note  
 Se `pFunctions` è null per l'input, `GetActiveFunctions` restituisce solo il numero di funzioni sullo stack. Vale a dire se `pFunctions` è null per l'input, `GetActiveFunctions` restituisce un valore solo in `pcFunctions`.  
  
 Il `GetActiveFunctions` metodo costituisce un'ottimizzazione acquisizione le stesse informazioni da una traccia dello stack frame e include solo i frame che sarebbe invece un oggetto ICorDebugILFrame per essi nell'analisi dello stack completo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
