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
ms.openlocfilehash: 4d3c3c0c5634653d14577de9a1334048d75216b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405626"
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
  
#### <a name="parameters"></a>Parametri  
 `fieldDef`  
 [in] Un campo `Def` token che fa riferimento il campo da recuperare.  
  
 `pFrame`  
 [in] Puntatore a un oggetto ICorDebugFrame che rappresenta il frame da utilizzare per distinguere tra i thread, di contesto o campi statici relativi al dominio di applicazione.  
  
 Se il campo statico è relativo a un thread, un contesto o dominio applicazione, il frame determina il valore appropriato.  
  
 `ppValue`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore del campo statico.  
  
## <a name="remarks"></a>Note  
 Per i tipi con parametri, il valore di un campo statico è rispetto alla creazione di un'istanza particolare. Pertanto, se il costruttore della classe accetta parametri di tipo <xref:System.Type>, chiamare [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) anziché `ICorDebugClass::GetStaticFieldValue`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
