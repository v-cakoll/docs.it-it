---
title: Metodo ICorDebugCode::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b6fd6e8043f1c62da8994b43a9b9af45fb2e3c0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700815"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="ba638-102">Metodo ICorDebugCode::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="ba638-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="ba638-103">Ottiene il numero in base 1 che identifica la versione del codice rappresentato da "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="ba638-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba638-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba638-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="ba638-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba638-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="ba638-106">out Puntatore al numero di versione del codice.</span><span class="sxs-lookup"><span data-stu-id="ba638-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba638-107">Note</span><span class="sxs-lookup"><span data-stu-id="ba638-107">Remarks</span></span>

 <span data-ttu-id="ba638-108">Il numero di versione viene incrementato ogni volta che viene eseguita un'operazione di modifica e continuazione (EnC) sul codice.</span><span class="sxs-lookup"><span data-stu-id="ba638-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba638-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba638-109">Requirements</span></span>

 <span data-ttu-id="ba638-110">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba638-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba638-111">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ba638-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba638-112">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba638-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba638-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba638-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
