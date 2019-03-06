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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f24a1434f737e8281a0c68dd09d2e17b34371694
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471654"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a>Metodo ICorDebugArrayValue::GetBaseIndicies
Ottiene l'indice di base di ogni dimensione della matrice.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cdim`  
 [in] Il numero di dimensioni di questo `ICorDebugArrayValue` oggetto. Questo valore viene anche le dimensioni dei `indicies` matrice perché la dimensione è uguale al numero di dimensioni del `ICorDebugArrayValue` oggetto.  
  
 `indicies`  
 [out] Matrice di interi, ognuno dei quali è l'indice di base (vale a dire, l'indice iniziale) di una dimensione di questo `ICorDebugArrayValue` oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
