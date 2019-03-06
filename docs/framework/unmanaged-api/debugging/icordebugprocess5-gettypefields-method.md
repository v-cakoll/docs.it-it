---
title: Metodo ICorDebugProcess5::GetTypeFields
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0aef54b1ddab9b2ccc0bfcfe8974a65831f70450
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477998"
---
# <a name="icordebugprocess5gettypefields-method"></a>Metodo ICorDebugProcess5::GetTypeFields
Vengono fornite informazioni sui campi che appartengono a un tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `id`  
 [in] L'identificatore del tipo le cui informazioni di campo viene recuperati.  
  
 `celt`  
 [in] I numerosi [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) oggetti le cui informazioni di campo deve essere recuperato.  
  
 `fields`  
 [out] Matrice di [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) gli oggetti che forniscono informazioni sui campi che appartengono al tipo.  
  
 `pceltNeeded`  
 [out] Un puntatore al numero di [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) oggetti inclusi nel `fields`.  
  
## <a name="remarks"></a>Note  
 Il `celt` parametro che specifica il numero di campi cui informazioni di campo, il metodo viene utilizzato per popolare `fields`, deve corrispondere al valore della `COR_TYPE_LAYOUT::numFields` campo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
