---
title: Metodo ICorDebugArrayValue::HasBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: 418ebb51df3f2d86011ee2e77022c3ee5c7ac0b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088226"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a>Metodo ICorDebugArrayValue::HasBaseIndicies
Ottiene un valore che indica se le dimensioni di questa matrice hanno un indice di base di diverso da zero.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbHasBaseIndicies`  
 out Puntatore a un valore booleano che viene `true` se una o più dimensioni di questo oggetto `ICorDebugArrayValue` hanno un indice di base diverso da zero; in caso contrario, il valore booleano viene `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]
