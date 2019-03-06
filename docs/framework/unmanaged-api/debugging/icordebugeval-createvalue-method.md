---
title: Metodo ICorDebugEval::CreateValue
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c16f6d1334888fc389a7c39cf0a3865afca2085
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471044"
---
# <a name="icordebugevalcreatevalue-method"></a>Metodo ICorDebugEval::CreateValue
Crea un valore del tipo specificato, con un valore iniziale pari a zero o null.  
  
 Questo metodo è obsoleto in .NET Framework versione 2.0. Uso [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Valore di [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumerazione che specifica il tipo del valore.  
  
 `pElementClass`  
 [in] Puntatore a un [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) oggetto che specifica la classe del valore, se il tipo non è un tipo primitivo.  
  
 `ppValue`  
 [out] Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore.  
  
## <a name="remarks"></a>Note  
 `CreateValue` Crea un `ICorDebugValue` oggetto del tipo specificato al solo scopo di utilizzo in una valutazione della funzione. Questo oggetto di valore è utilizzabile per passare le costanti di utente come parametri.  
  
 Se il tipo del valore è un tipo primitivo, il valore iniziale è pari a zero o null. Uso [ICorDebugGenericValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) per impostare il valore di un tipo primitivo.  
  
 Se il valore di `elementType` è ELEMENT_TYPE_CLASS, si ottiene un' "interfaccia ICorDebugReferenceValue" (restituite in `ppValue`) che rappresenta il riferimento all'oggetto null. È possibile utilizzare questa oggetto passare null per una valutazione della funzione con parametri per riferimento oggetto. Non è possibile impostare il `ICorDebugValue` ad alcun elemento; rimane sempre null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche

- [Metodo CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [ICorDebugEval (interfaccia)](icordebugeval-interface.md)
