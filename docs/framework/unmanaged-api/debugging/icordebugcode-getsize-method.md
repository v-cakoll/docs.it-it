---
title: Metodo ICorDebugCode::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
ms.openlocfilehash: 2370ff5d99078ceb1ae0509e660c046dd7a1537e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125613"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="e5fe5-102">Metodo ICorDebugCode::GetSize</span><span class="sxs-lookup"><span data-stu-id="e5fe5-102">ICorDebugCode::GetSize Method</span></span>

<span data-ttu-id="e5fe5-103">Ottiene la dimensione, in byte, del codice binario rappresentato da questo "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="e5fe5-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>

## <a name="syntax"></a><span data-ttu-id="e5fe5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5fe5-104">Syntax</span></span>

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a><span data-ttu-id="e5fe5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5fe5-105">Parameters</span></span>

`pcBytes`  
<span data-ttu-id="e5fe5-106">out Puntatore alla dimensione, in byte, del codice binario rappresentato da questo oggetto `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="e5fe5-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>

## <a name="requirements"></a><span data-ttu-id="e5fe5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5fe5-107">Requirements</span></span>

<span data-ttu-id="e5fe5-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5fe5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e5fe5-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5fe5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="e5fe5-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5fe5-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e5fe5-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5fe5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
