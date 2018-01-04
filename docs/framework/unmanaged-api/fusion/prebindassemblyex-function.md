---
title: Funzione PreBindAssemblyEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PreBindAssemblyEx
api_location: fusion.dll
api_type: DLLExport
f1_keywords: PreBindAssemblyEx
helpviewer_keywords: PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05977db8e01d00af6e160cb2993867cf83eb24c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="c22f2-102">Funzione PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="c22f2-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="c22f2-103">Ottiene il nome visualizzato di post-criteri per un assembly.</span><span class="sxs-lookup"><span data-stu-id="c22f2-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="c22f2-104">Questa funzione supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="c22f2-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22f2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c22f2-105">Syntax</span></span>  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c22f2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c22f2-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="c22f2-107">[in] Identifica il contesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c22f2-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="c22f2-108">[in] Identifica il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c22f2-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="c22f2-109">[in] Identifica l'assembly padre.</span><span class="sxs-lookup"><span data-stu-id="c22f2-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="c22f2-110">Questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="c22f2-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="c22f2-111">[in] Identifica la versione di runtime.</span><span class="sxs-lookup"><span data-stu-id="c22f2-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="c22f2-112">[out] Contiene il nome visualizzato di post-criteri.</span><span class="sxs-lookup"><span data-stu-id="c22f2-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="c22f2-113">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="c22f2-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c22f2-114">`pvReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="c22f2-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c22f2-115">Note</span><span class="sxs-lookup"><span data-stu-id="c22f2-115">Remarks</span></span>  
 <span data-ttu-id="c22f2-116">Il `ppNamePostPolicy` parametro di output viene impostato solo se la funzione restituisce HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="c22f2-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="c22f2-117">In caso contrario, è null.</span><span class="sxs-lookup"><span data-stu-id="c22f2-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c22f2-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c22f2-118">Requirements</span></span>  
 <span data-ttu-id="c22f2-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c22f2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c22f2-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c22f2-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c22f2-121">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c22f2-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c22f2-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c22f2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22f2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c22f2-123">See Also</span></span>  
 [<span data-ttu-id="c22f2-124">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="c22f2-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
