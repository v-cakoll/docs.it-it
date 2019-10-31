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
ms.openlocfilehash: 0809a149a5a5a5e9adea059140d7b4b456337ef3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125309"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="9d4c3-102">Metodo ICorDebugModule2::ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="9d4c3-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="9d4c3-103">Risolve l'assembly a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="9d4c3-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d4c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d4c3-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="9d4c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d4c3-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="9d4c3-106">in Valore `mdToken` che fa riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d4c3-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="9d4c3-107">out Puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d4c3-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d4c3-108">Note</span><span class="sxs-lookup"><span data-stu-id="9d4c3-108">Remarks</span></span>

<span data-ttu-id="9d4c3-109">Se l'assembly non è già caricato quando viene chiamato `ResolveAssembly`, viene restituito un valore HRESULT di CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="9d4c3-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="9d4c3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d4c3-110">Requirements</span></span>

<span data-ttu-id="9d4c3-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d4c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9d4c3-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d4c3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="9d4c3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d4c3-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9d4c3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d4c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
