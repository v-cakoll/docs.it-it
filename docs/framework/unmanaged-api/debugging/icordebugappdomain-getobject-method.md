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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895217"
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
 Se un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito non è stato costruito per questo dominio dell'applicazione, il `S_FALSE` metodo restituisce `NULL` e `*ppObject`inserisce in.  
  
## <a name="remarks"></a>Osservazioni  
 Ogni dominio applicazione in un processo può avere un oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito nel runtime che lo rappresenta. Questa funzione ottiene un oggetto interfaccia ICorDebugValue che corrisponde a questo oggetto <xref:System.AppDomain?displayProperty=nameWithType> gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
