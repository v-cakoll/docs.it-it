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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c0f4836a3dc848b52ee7fe6947f350e6fab787f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737559"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a>Metodo ICorDebugArrayValue::GetDimensions
Ottiene il numero di elementi in ogni dimensione di questa matrice.  
  
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
 [in] Il numero di dimensioni dell'oggetto ICorDebugArrayValue.  
  
 Questo valore viene anche le dimensioni dei `dims` matrice perché la dimensione è uguale al numero di dimensioni del `ICorDebugArrayValue` oggetto.  
  
 `dims`  
 [out] Matrice di interi, ognuno dei quali specifica il numero di elementi in una dimensione in questo `ICorDebugArrayValue` oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
