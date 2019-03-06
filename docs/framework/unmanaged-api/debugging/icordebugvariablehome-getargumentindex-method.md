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
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366829"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="97f9a-102">Metodo ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="97f9a-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="97f9a-103">Ottiene l'indice di un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="97f9a-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="97f9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97f9a-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="97f9a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97f9a-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="97f9a-106">[out] Un puntatore all'indice di argomento.</span><span class="sxs-lookup"><span data-stu-id="97f9a-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="97f9a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97f9a-107">Return Value</span></span>

<span data-ttu-id="97f9a-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="97f9a-108">The method returns the following values.</span></span>

|<span data-ttu-id="97f9a-109">Valore</span><span class="sxs-lookup"><span data-stu-id="97f9a-109">Value</span></span>|<span data-ttu-id="97f9a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97f9a-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="97f9a-111">La chiamata al metodo ha restituito un indice di argomento valido.</span><span class="sxs-lookup"><span data-stu-id="97f9a-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="97f9a-112">L'oggetto corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="97f9a-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="97f9a-113">Note</span><span class="sxs-lookup"><span data-stu-id="97f9a-113">Remarks</span></span>

<span data-ttu-id="97f9a-114">L'indice dell'argomento è utilizzabile per recuperare i metadati per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="97f9a-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="97f9a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97f9a-115">Requirements</span></span>

<span data-ttu-id="97f9a-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97f9a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="97f9a-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97f9a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="97f9a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97f9a-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="97f9a-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f9a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="97f9a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97f9a-120">See also</span></span>

- [<span data-ttu-id="97f9a-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="97f9a-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
