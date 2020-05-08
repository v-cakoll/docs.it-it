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
ms.openlocfilehash: 9aadbe7c6f18c6b15350267d1f9ecaa3a23cdd20
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895075"
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
 in Numero di dimensioni dell' `ICorDebugArrayValue` oggetto. Questo valore corrisponde anche alla dimensione della `indicies` matrice perché la relativa dimensione è uguale al numero di dimensioni dell' `ICorDebugArrayValue` oggetto.  
  
 `indicies`  
 out Matrice di Integer, ognuno dei quali è l'indice di base, ovvero l'indice iniziale, di una dimensione di questo `ICorDebugArrayValue` oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
