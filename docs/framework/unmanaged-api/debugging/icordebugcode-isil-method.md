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
ms.openlocfilehash: 0a81f4a53954c559ab12e27bcf039b7b1a1804cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700789"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="92302-102">Metodo ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="92302-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="92302-103">Ottiene un valore che indica se questo "ICorDebugCode" rappresenta il codice compilato in MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="92302-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="92302-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92302-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="92302-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="92302-105">Parameters</span></span>
 `pbIL`  
 <span data-ttu-id="92302-106">[out] `true` se questo `ICorDebugCode` rappresenta il codice compilato in MSIL; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="92302-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="92302-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92302-107">Requirements</span></span>

 <span data-ttu-id="92302-108">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92302-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  

 <span data-ttu-id="92302-109">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="92302-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  

 <span data-ttu-id="92302-110">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92302-110">**Library:** CorGuids.lib</span></span>  

 <span data-ttu-id="92302-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92302-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
 
