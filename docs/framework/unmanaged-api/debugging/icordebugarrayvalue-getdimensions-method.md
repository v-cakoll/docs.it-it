---
title: Metodo ICorDebugArrayValue::GetDimensions
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: fa2be894af6e44d09c25a736f45acba56052f9fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895047"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a>Metodo ICorDebugArrayValue::GetDimensions
Ottiene il numero di elementi in ogni dimensione della matrice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cdim`  
 in Numero di dimensioni di questo oggetto ICorDebugArrayValue.  
  
 Questo valore corrisponde anche alla dimensione della `dims` matrice perché la relativa dimensione è uguale al numero di dimensioni dell' `ICorDebugArrayValue` oggetto.  
  
 `dims`  
 out Matrice di Integer, ognuno dei quali specifica il numero di elementi in una dimensione in questo `ICorDebugArrayValue` oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
