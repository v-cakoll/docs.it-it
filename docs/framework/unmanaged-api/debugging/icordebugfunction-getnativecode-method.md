---
title: Metodo ICorDebugFunction::GetNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 98aee38415709974d84873df50c39263490f2f23
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213270"
---
# <a name="icordebugfunctiongetnativecode-method"></a>Metodo ICorDebugFunction::GetNativeCode
Ottiene il codice nativo per la funzione rappresentata da questa istanza di ICorDebugFunction.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppCode`  
 out Puntatore all'istanza di ICorDebugCode che rappresenta il codice nativo per questa funzione, o null, se questa funzione è codice MSIL (Microsoft Intermediate Language) che non è stato compilato just-in-time (JIT).  
  
## <a name="remarks"></a>Osservazioni  
 Se la funzione rappresentata da questa `ICorDebugFunction` istanza è stata compilata tramite JIT più di una volta, come nel caso dei tipi generici, `GetNativeCode` restituisce un oggetto di codice nativo casuale.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
