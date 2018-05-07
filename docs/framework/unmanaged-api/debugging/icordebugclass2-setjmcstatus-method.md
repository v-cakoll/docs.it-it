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
ms.openlocfilehash: d234e01e3d47a64b9a001591ee2b61074eea8afb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugclass2setjmcstatus-method"></a>Metodo ICorDebugClass2::SetJMCStatus
Per ogni metodo della classe, imposta un valore che indica se il metodo è codice definito dall'utente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bIsJustMyCode`  
 [in] Impostare su `true` per indicare che il metodo è definito dall'utente codice; in caso contrario, impostato su `false`.  
  
## <a name="remarks"></a>Note  
 Un just my code (JMC) ignorerà il codice non definito dall'utente. Codice definito dall'utente deve essere un subset di debug.  
  
 `SetJMCStatus` Restituisce un valore HRESULT di S_FALSE se risulta impossibile impostare il valore per tutti i metodi, anche se è stata imposta il valore per tutti gli altri metodi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
