---
title: Metodo ICorDebugAppDomain2::GetFunctionPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
ms.openlocfilehash: 5a6e0b009674ff52595aaa0ae4a060f1cdfd1398
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089054"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a>Metodo ICorDebugAppDomain2::GetFunctionPointerType
Ottiene un puntatore a una funzione con una firma specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nTypeArgs`  
 in Numero di argomenti di tipo per la funzione.  
  
 `ppTypeArgs`  
 in Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo della funzione. Il primo elemento è il tipo restituito. ognuno degli altri elementi è un tipo di parametro.  
  
 `ppType`  
 out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il puntatore alla funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
