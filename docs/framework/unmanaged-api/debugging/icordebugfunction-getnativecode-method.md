---
title: Metodo ICorDebugFunction::GetNativeCode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetNativeCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fccfaeb346d59f5cf565f47a9a64e732706adad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetnativecode-method"></a>Metodo ICorDebugFunction::GetNativeCode
Ottiene il codice nativo per la funzione che è rappresentata da questa istanza di ICorDebugFunction.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppCode`  
 [out] Un puntatore all'istanza di ICorDebugCode che rappresenta il codice nativo per questa funzione, o null, se questa funzione è codice Microsoft intermediate language (MSIL) che non è stato just-in-time (JIT) compilati.  
  
## <a name="remarks"></a>Note  
 Se la funzione che è rappresentata da questo `ICorDebugFunction` istanza è stata compilata tramite JIT più volte, come nel caso di tipi generici, `GetNativeCode` restituisce un oggetto di codice nativo casuale.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
