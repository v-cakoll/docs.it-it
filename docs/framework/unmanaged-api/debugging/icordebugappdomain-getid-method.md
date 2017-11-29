---
title: Metodo ICorDebugAppDomain::GetId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetId
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5a8dcbc1fd710513b2b27e92f4d2e1e1b5c72092
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="defe6-102">Metodo ICorDebugAppDomain::GetId</span><span class="sxs-lookup"><span data-stu-id="defe6-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="defe6-103">Ottiene l'identificatore univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="defe6-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="defe6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="defe6-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="defe6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="defe6-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="defe6-106">[out] Identificatore univoco del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="defe6-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="defe6-107">Note</span><span class="sxs-lookup"><span data-stu-id="defe6-107">Remarks</span></span>  
 <span data-ttu-id="defe6-108">L'identificatore per il dominio applicazione è univoco all'interno del processo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="defe6-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="defe6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="defe6-109">Requirements</span></span>  
 <span data-ttu-id="defe6-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="defe6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="defe6-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="defe6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="defe6-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="defe6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="defe6-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="defe6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
