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
ms.openlocfilehash: 7c6d1905cdbd12b960014e687034ea9d163b68d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179030"
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
 [in] Numero di dimensioni `ICorDebugArrayValue` di questo oggetto. Questo valore è anche `indicies` la dimensione della matrice perché la sua `ICorDebugArrayValue` dimensione è uguale al numero di dimensioni dell'oggetto.  
  
 `indicies`  
 [fuori] Matrice di interi, ognuno dei quali è l'indice di base (ovvero l'indice iniziale) di una dimensione di questo `ICorDebugArrayValue` oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
