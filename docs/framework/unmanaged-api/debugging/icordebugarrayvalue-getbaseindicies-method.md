---
title: Metodo ICorDebugArrayValue::GetBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: e103401b85626e53db53e1894c22b161774e5163
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088681"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a>Metodo ICorDebugArrayValue::GetBaseIndicies
Ottiene l'indice di base di ogni dimensione nella matrice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cdim`  
 in Numero di dimensioni dell'oggetto `ICorDebugArrayValue`. Questo valore corrisponde anche alla dimensione della matrice `indicies` perché la relativa dimensione è uguale al numero di dimensioni dell'oggetto `ICorDebugArrayValue`.  
  
 `indicies`  
 out Matrice di Integer, ognuno dei quali è l'indice di base, ovvero l'indice iniziale, di una dimensione di questo oggetto `ICorDebugArrayValue`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
