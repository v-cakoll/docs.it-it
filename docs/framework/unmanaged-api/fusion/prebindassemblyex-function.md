---
title: Funzione PreBindAssemblyEx
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d3e2535851d39be642de56a86b78c328ecaf446
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432001"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="30bad-102">Funzione PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="30bad-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="30bad-103">Ottiene il nome visualizzato di post-criteri per un assembly.</span><span class="sxs-lookup"><span data-stu-id="30bad-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="30bad-104">Questa funzione supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="30bad-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30bad-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30bad-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="30bad-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="30bad-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="30bad-107">[in] Identifica il contesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="30bad-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="30bad-108">[in] Identifica il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="30bad-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="30bad-109">[in] Identifica l'assembly padre.</span><span class="sxs-lookup"><span data-stu-id="30bad-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="30bad-110">Questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="30bad-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="30bad-111">[in] Identifica la versione di runtime.</span><span class="sxs-lookup"><span data-stu-id="30bad-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="30bad-112">[out] Contiene il nome visualizzato di post-criteri.</span><span class="sxs-lookup"><span data-stu-id="30bad-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="30bad-113">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="30bad-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="30bad-114">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="30bad-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30bad-115">Note</span><span class="sxs-lookup"><span data-stu-id="30bad-115">Remarks</span></span>  
 <span data-ttu-id="30bad-116">Il `ppNamePostPolicy` parametro di output viene impostato solo se la funzione restituisce HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="30bad-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="30bad-117">In caso contrario, è null.</span><span class="sxs-lookup"><span data-stu-id="30bad-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30bad-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30bad-118">Requirements</span></span>  
 <span data-ttu-id="30bad-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30bad-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30bad-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="30bad-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="30bad-121">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="30bad-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30bad-122">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30bad-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30bad-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30bad-123">See Also</span></span>  
 [<span data-ttu-id="30bad-124">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="30bad-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
