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
ms.openlocfilehash: 500e01955666c7a8e2bd1dcf9d34afe3aeb6b421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403344"
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
  
#### <a name="parameters"></a>Parametri  
 `cdim`  
 [in] Il numero di dimensioni di questo `ICorDebugArrayValue` oggetto.  
  
 Questo valore corrisponde anche alla dimensione del `indices` matrice perché la dimensione è uguale al numero di dimensioni del `ICorDebugArrayValue` oggetto.  
  
 `indices`  
 [in] Una matrice di valori di indice, ognuno dei quali specifica una posizione all'interno di una dimensione di `ICorDebugArrayValue` oggetto.  
  
 Questo valore non deve essere null.  
  
 `ppValue`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore dell'elemento specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
