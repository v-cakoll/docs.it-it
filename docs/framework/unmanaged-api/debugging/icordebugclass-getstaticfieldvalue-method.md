---
title: Metodo ICorDebugClass::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b67f5ec233679461f61715d7562b47c2a195fb8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471628"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>Metodo ICorDebugClass::GetStaticFieldValue
Ottiene il valore del campo statico specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fieldDef`  
 [in] Un campo `Def` token che fa riferimento al campo da recuperare.  
  
 `pFrame`  
 [in] Un puntatore a un oggetto ICorDebugFrame che rappresenta la cornice per essere usato per distinguere tra thread, al contesto o campi statici relativi al dominio dell'applicazione.  
  
 Se il campo statico è rispetto a un thread, un contesto o un dominio dell'applicazione, il frame determinerà il valore appropriato.  
  
 `ppValue`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore del campo statico.  
  
## <a name="remarks"></a>Note  
 Per i tipi con parametri, il valore di un campo statico è relativo alla creazione di un'istanza particolare. Pertanto, se il costruttore della classe accetta i parametri di tipo <xref:System.Type>, chiamare [GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) invece di `ICorDebugClass::GetStaticFieldValue`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
