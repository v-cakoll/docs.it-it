---
title: Metodo ICLRRuntimeInfo::IsLoadable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d3825f8dc529cf9c5fbfc44ae70008695e32054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="39f6b-102">Metodo ICLRRuntimeInfo::IsLoadable</span><span class="sxs-lookup"><span data-stu-id="39f6b-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="39f6b-103">Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, prendendo in considerazione altri runtime che potrebbero essere già stato caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="39f6b-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39f6b-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39f6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39f6b-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="39f6b-106">[out] `true` se il runtime può essere caricato nel processo corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="39f6b-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39f6b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="39f6b-107">Return Value</span></span>  
 <span data-ttu-id="39f6b-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="39f6b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="39f6b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39f6b-109">HRESULT</span></span>|<span data-ttu-id="39f6b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39f6b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39f6b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="39f6b-111">S_OK</span></span>|<span data-ttu-id="39f6b-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="39f6b-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="39f6b-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="39f6b-113">E_POINTER</span></span>|<span data-ttu-id="39f6b-114">`pbLoadable` è null.</span><span class="sxs-lookup"><span data-stu-id="39f6b-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39f6b-115">Note</span><span class="sxs-lookup"><span data-stu-id="39f6b-115">Remarks</span></span>  
 <span data-ttu-id="39f6b-116">Se un altro runtime è già caricato nel processo e il runtime associato a questa interfaccia può essere caricato per l'esecuzione side-by-side in-process, `pbLoadable` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="39f6b-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="39f6b-117">Se i due runtime non è possibile eseguire side-by-side in-process, `pbLoadable` restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="39f6b-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="39f6b-118">Ad esempio, common language runtime (CLR) versione 4 è possibile eseguire side-by-side nello stesso processo CLR versione 2.0 o CLR versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="39f6b-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="39f6b-119">Tuttavia, CLR versione 1.1 e 2.0 di CLR non è possibile eseguire side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="39f6b-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="39f6b-120">Se non sono presenti runtime vengono caricati nel processo, questo metodo restituisce sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="39f6b-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39f6b-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39f6b-121">Requirements</span></span>  
 <span data-ttu-id="39f6b-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39f6b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f6b-123">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="39f6b-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39f6b-124">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39f6b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39f6b-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39f6b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f6b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39f6b-126">See Also</span></span>  
 [<span data-ttu-id="39f6b-127">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="39f6b-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="39f6b-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="39f6b-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="39f6b-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="39f6b-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
