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
ms.openlocfilehash: 646c20ca1b78ff0ce513b8a3c9b578c3b1b9a696
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125609"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="5d560-102">Metodo ICorDebugCode::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="5d560-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="5d560-103">Ottiene il numero in base 1 che identifica la versione del codice rappresentato da "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="5d560-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d560-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d560-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="5d560-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d560-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="5d560-106">out Puntatore al numero di versione del codice.</span><span class="sxs-lookup"><span data-stu-id="5d560-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d560-107">Note</span><span class="sxs-lookup"><span data-stu-id="5d560-107">Remarks</span></span>

 <span data-ttu-id="5d560-108">Il numero di versione viene incrementato ogni volta che viene eseguita un'operazione di modifica e continuazione (EnC) sul codice.</span><span class="sxs-lookup"><span data-stu-id="5d560-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d560-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d560-109">Requirements</span></span>

 <span data-ttu-id="5d560-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d560-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d560-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d560-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d560-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d560-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d560-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d560-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
