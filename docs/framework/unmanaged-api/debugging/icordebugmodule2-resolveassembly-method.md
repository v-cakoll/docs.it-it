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
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210034"
---
# <a name="icordebugmodule2resolveassembly-method"></a>Metodo ICorDebugModule2::ResolveAssembly

Risolve l'assembly a cui fa riferimento il token di metadati specificato.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>Parametri

`tkAssemblyRef`\
in `mdToken`Valore che fa riferimento all'assembly.

`ppAssembly`\
out Puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly.

## <a name="remarks"></a>Osservazioni

Se l'assembly non è già caricato quando `ResolveAssembly` viene chiamato il metodo, viene restituito un valore HRESULT di CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
