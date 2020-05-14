---
title: 'Metodo metodo icordebugtype2:: GetTypeID'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 1c11946bc5ea69a090091c014aba859935b48b36
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396667"
---
# <a name="icordebugtype2gettypeid-method"></a>Metodo metodo icordebugtype2:: GetTypeID
Ottiene un [COR_TYPEID](cor-typeid-structure.md) per questo tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `id`  
 out Puntatore al [COR_TYPEID](cor-typeid-structure.md) per questo ICorDebugType.  
  
## <a name="return-value"></a>Valore restituito  
 Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo. I `HRESULT` codici includono i seguenti:  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|`S_OK`|Il metodo è riuscito. Il metodo ha recuperato un [COR_TYPEID](cor-typeid-structure.md)valido.|  
|`CORDBG_E_CLASS_NOT_LOADED`|Il tipo non è stato caricato.|  
|`CORDBG_E_UNSUPPORTED`|Il tipo non è supportato.|  
  
## <a name="remarks"></a>Commenti  
 Questo metodo fornisce un mapping da ICorDebugType, che rappresenta un tipo che può essere caricato o meno nel runtime, in una [COR_TYPEID](cor-typeid-structure.md), che funge da handle opaco che identifica un tipo caricato nel Runtime.  
  
 Quando il tipo rappresentato da ICorDebugType non è ancora stato caricato, questo metodo restituisce `CORDBG_E_CLASS_NOT_LOADED` .  Se il tipo non è supportato, restituisce `CORDBG_E_UNSUPPORTED` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugType2](icordebugtype2-interface.md)
