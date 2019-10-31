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
ms.openlocfilehash: 0045285a3da22f468c2426bb3b9c4ae7e3e1d7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132664"
---
# <a name="icordebugprocess5gettypefields-method"></a>Metodo ICorDebugProcess5::GetTypeFields
Fornisce informazioni sui campi che appartengono a un tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `id`  
 in Identificatore del tipo le cui informazioni sul campo vengono recuperate.  
  
 `celt`  
 in Numero di oggetti [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) di cui è necessario recuperare le informazioni sul campo.  
  
 `fields`  
 out Matrice di oggetti [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) che forniscono informazioni sui campi che appartengono al tipo.  
  
 `pceltNeeded`  
 out Puntatore al numero di oggetti [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) inclusi nel `fields`.  
  
## <a name="remarks"></a>Note  
 Il parametro `celt`, che specifica il numero di campi le cui informazioni sul campo utilizzate dal metodo per popolare `fields`, devono corrispondere al valore del campo `COR_TYPE_LAYOUT::numFields`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
