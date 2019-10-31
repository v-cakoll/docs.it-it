---
title: Metodo ICorDebugAppDomain::GetId
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
ms.openlocfilehash: 87c43d6f05dffbf10ca1dd9253abfe893db9adf5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110472"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="6151c-102">Metodo ICorDebugAppDomain::GetId</span><span class="sxs-lookup"><span data-stu-id="6151c-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="6151c-103">Ottiene l'identificatore univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6151c-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6151c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6151c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6151c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6151c-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="6151c-106">out Identificatore univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6151c-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6151c-107">Note</span><span class="sxs-lookup"><span data-stu-id="6151c-107">Remarks</span></span>  
 <span data-ttu-id="6151c-108">L'identificatore per il dominio dell'applicazione è univoco all'interno del processo contenitore.</span><span class="sxs-lookup"><span data-stu-id="6151c-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6151c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6151c-109">Requirements</span></span>  
 <span data-ttu-id="6151c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6151c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6151c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6151c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6151c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6151c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6151c-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6151c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
