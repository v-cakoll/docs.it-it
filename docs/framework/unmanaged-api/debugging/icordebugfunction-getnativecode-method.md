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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb85c4b2c26c136a5f9fc05221a42c4bc99f37f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470172"
---
# <a name="icordebugfunctiongetnativecode-method"></a>Metodo ICorDebugFunction::GetNativeCode
Ottiene il codice nativo per la funzione rappresentata da questa istanza ICorDebugFunction.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppCode`  
 [out] Un puntatore all'istanza ICorDebugCode che rappresenta il codice nativo per questa funzione, o null, se questa funzione è codice Microsoft intermediate language (MSIL) che non è stato just-in-time (JIT) compilato.  
  
## <a name="remarks"></a>Note  
 Se la funzione rappresentata da questo `ICorDebugFunction` istanza è stata compilata tramite JIT più di una volta, come nel caso di tipi generici, `GetNativeCode` restituisce un oggetto di codice nativa casuale.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
