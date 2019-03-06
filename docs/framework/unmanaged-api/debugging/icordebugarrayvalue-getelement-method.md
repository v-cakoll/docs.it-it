---
title: Metodo ICorDebugArrayValue::GetElement
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be7eaeccb53e8b180aeb9492cd887f952bbaea5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485304"
---
# <a name="icordebugarrayvaluegetelement-method"></a>Metodo ICorDebugArrayValue::GetElement
Ottiene il valore dell'elemento della matrice specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cdim`  
 [in] Il numero di dimensioni di questo `ICorDebugArrayValue` oggetto.  
  
 Questo valore viene anche le dimensioni dei `indices` matrice perché la dimensione è uguale al numero di dimensioni del `ICorDebugArrayValue` oggetto.  
  
 `indices`  
 [in] Una matrice di valori di indice, ognuno dei quali specifica una posizione all'interno di una dimensione del `ICorDebugArrayValue` oggetto.  
  
 Questo valore non deve essere null.  
  
 `ppValue`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
