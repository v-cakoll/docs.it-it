---
title: Metodo ICorDebugEval::CreateValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CreateValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64d55a951795cc5efc1bfc624dbe07575be153aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalcreatevalue-method"></a>Metodo ICorDebugEval::CreateValue
Crea un valore del tipo specificato, con un valore iniziale pari a zero o null.  
  
 Questo metodo è obsoleto in .NET Framework versione 2.0. Utilizzare [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Il valore di [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumerazione che specifica il tipo del valore.  
  
 `pElementClass`  
 [in] Puntatore a un [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) oggetto che specifica la classe di valore, se il tipo non è un tipo primitivo.  
  
 `ppValue`  
 [out] Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore.  
  
## <a name="remarks"></a>Note  
 `CreateValue`Crea un `ICorDebugValue` oggetto del tipo specificato al solo scopo di utilizzo in una valutazione della funzione. Questo oggetto valore utilizzabile per passare le costanti utente come parametri.  
  
 Se il tipo del valore è un tipo primitivo, il valore iniziale è zero o null. Utilizzare [ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) per impostare il valore di un tipo primitivo.  
  
 Se il valore di `elementType` è ELEMENT_TYPE_CLASS, si ottiene un'interfaccia "ICorDebugReferenceValue" (restituiti in `ppValue`) che rappresenta il riferimento di oggetto null. Passare null per una valutazione della funzione che dispone di parametri di riferimento di oggetto, è possibile utilizzare questo oggetto. Non è possibile impostare il `ICorDebugValue` effettuare alcuna azione; rimane sempre null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche  
    
 [Metodo CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 ICorDebugValue
