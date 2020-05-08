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
ms.openlocfilehash: 63346c679efc083dea9ab0eaa4f983a5308695f8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895246"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="9410f-102">Metodo ICorDebugAppDomain::GetId</span><span class="sxs-lookup"><span data-stu-id="9410f-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="9410f-103">Ottiene l'identificatore univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9410f-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9410f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9410f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9410f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9410f-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="9410f-106">out Identificatore univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9410f-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9410f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9410f-107">Remarks</span></span>  
 <span data-ttu-id="9410f-108">L'identificatore per il dominio dell'applicazione è univoco all'interno del processo contenitore.</span><span class="sxs-lookup"><span data-stu-id="9410f-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9410f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9410f-109">Requirements</span></span>  
 <span data-ttu-id="9410f-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9410f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9410f-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9410f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9410f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9410f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9410f-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9410f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
