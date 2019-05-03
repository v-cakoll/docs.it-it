---
title: Metodo ICorDebugModule2::ResolveAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994825"
---
# <a name="icordebugmodule2resolveassembly-method"></a>Metodo ICorDebugModule2::ResolveAssembly

Risolve l'assembly fa riferimento il token di metadati specificato.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>Parametri

`tkAssemblyRef`\
[in] Un `mdToken` valore cui fa riferimento all'assembly.

`ppAssembly`\
[out] Un puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly.

## <a name="remarks"></a>Note

Se l'assembly non è già caricata quando `ResolveAssembly` viene chiamato, un valore HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY come valore restituito.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
