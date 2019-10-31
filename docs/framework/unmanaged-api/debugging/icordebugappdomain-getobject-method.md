---
title: Metodo ICorDebugAppDomain::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134706"
---
# <a name="icordebugappdomaingetobject-method"></a>Metodo ICorDebugAppDomain::GetObject
Ottiene un puntatore a interfaccia per il dominio dell'applicazione Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppObject`  
 out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugValue che rappresenta il dominio applicazione CLR.  
  
## <a name="return-value"></a>Valore restituito  
 Se per questo dominio applicazione non è stato costruito un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito, il metodo restituisce `S_FALSE` e inserisce `NULL` in `*ppObject`.  
  
## <a name="remarks"></a>Note  
 Ogni dominio applicazione in un processo può avere un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito nel runtime che lo rappresenta. Questa funzione ottiene un oggetto interfaccia ICorDebugValue che corrisponde a questo oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
