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
ms.openlocfilehash: 7a52e61f41bd1d7f68523dd16f70010ffbba401e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895028"
---
# <a name="icordebugarrayvaluegetelement-method"></a>Metodo ICorDebugArrayValue::GetElement
Ottiene il valore dell'elemento di matrice specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cdim`  
 in Numero di dimensioni dell' `ICorDebugArrayValue` oggetto.  
  
 Questo valore corrisponde anche alla dimensione della `indices` matrice perché la relativa dimensione è uguale al numero di dimensioni dell' `ICorDebugArrayValue` oggetto.  
  
 `indices`  
 in Matrice di valori di indice, ognuno dei quali specifica una posizione all'interno di una dimensione `ICorDebugArrayValue` dell'oggetto.  
  
 Questo valore non può essere null.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
