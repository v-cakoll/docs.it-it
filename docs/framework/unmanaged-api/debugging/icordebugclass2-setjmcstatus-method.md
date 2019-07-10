---
title: Metodo ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23f248625753c15a4798ea69a1eb3b377b79f95d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747759"
---
# <a name="icordebugclass2setjmcstatus-method"></a>Metodo ICorDebugClass2::SetJMCStatus
Per ogni metodo della classe, imposta un valore che indica se il metodo è codice definito dall'utente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIsJustMyCode`  
 [in] Impostare su `true` per indicare che il metodo è definito dall'utente codice; in caso contrario, impostato su `false`.  
  
## <a name="remarks"></a>Note  
 Un just my code (JMC) ignorerà il codice non definito dall'utente. Codice definito dall'utente deve essere un subset di debug.  
  
 `SetJMCStatus` Restituisce un valore HRESULT di S_FALSE se non riesce a impostare il valore per qualsiasi metodo, anche se è stata imposta il valore per tutti gli altri metodi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
