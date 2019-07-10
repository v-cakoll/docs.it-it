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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737848"
---
# <a name="icordebugappdomaingetobject-method"></a>Metodo ICorDebugAppDomain::GetObject
Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppObject`  
 [out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugValue che rappresenta il dominio dell'applicazione CLR.  
  
## <a name="return-value"></a>Valore restituito  
 Se un oggetto gestito <xref:System.AppDomain?displayProperty=nameWithType> oggetto non è stato costruito per il dominio applicazione, il metodo restituisce `S_FALSE` e le inserisce `NULL` in `*ppObject`.  
  
## <a name="remarks"></a>Note  
 Ogni dominio dell'applicazione in un processo potrebbe essere un oggetto gestito <xref:System.AppDomain?displayProperty=nameWithType> oggetto in fase di esecuzione che lo rappresenta. Questa funzione Ottiene un oggetto di interfaccia ICorDebugValue che corrisponde a questo gestiti <xref:System.AppDomain?displayProperty=nameWithType> oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
