---
title: Metodo ICorDebugModule::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
ms.openlocfilehash: a33b6ff308f3444496e5a1cb2e04f28e80305db5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212581"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>Metodo ICorDebugModule::GetFunctionFromToken
Ottiene la funzione specificata dal token di metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `methodDef`  
 in `mdMethodDef`Token di metadati che fa riferimento ai metadati della funzione.  
  
 `ppFunction`  
 out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugFunction che rappresenta la funzione.  
  
## <a name="remarks"></a>Osservazioni  
 Il `GetFunctionFromToken` metodo restituisce un CORDBG_E_FUNCTION_NOT_IL HRESULT se il valore passato non `methodDef` fa riferimento a un metodo MSIL (Microsoft Intermediate Language).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
