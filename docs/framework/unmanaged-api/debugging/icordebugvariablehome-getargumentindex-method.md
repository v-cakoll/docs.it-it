---
title: Metodo ICorDebugVariableHome::GetArgumentIndex
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2457dff3063e47f1fb9d040caac1bc08441e1739
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986791"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>Metodo ICorDebugVariableHome::GetArgumentIndex

Ottiene l'indice di un argomento di funzione.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Parametri

`pArgumentIndex`\
[out] Un puntatore all'indice di argomento.

## <a name="return-value"></a>Valore restituito

Il metodo restituisce i valori seguenti.

|Value|Descrizione|
|-----------|-----------------|
|`S_OK`|La chiamata al metodo ha restituito un indice di argomento valido.|
|`E_FAIL`|L'oggetto corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta una variabile locale.|

## <a name="remarks"></a>Note

L'indice dell'argomento è utilizzabile per recuperare i metadati per questo argomento.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
