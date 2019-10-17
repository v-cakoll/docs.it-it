---
title: Metodo ICorDebugCode::IsIL
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b7cbadbd1494d5e4d1488dd12296f4f90890127
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395491"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="0a659-102">Metodo ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="0a659-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="0a659-103">Ottiene un valore che indica se questo "ICorDebugCode" rappresenta il codice compilato in MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="0a659-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="0a659-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a659-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="0a659-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a659-105">Parameters</span></span>

`pbIL`  
<span data-ttu-id="0a659-106">[out] `true` se questo `ICorDebugCode` rappresenta il codice compilato in MSIL; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0a659-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a659-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a659-107">Requirements</span></span>

<span data-ttu-id="0a659-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a659-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0a659-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a659-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="0a659-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a659-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0a659-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a659-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
