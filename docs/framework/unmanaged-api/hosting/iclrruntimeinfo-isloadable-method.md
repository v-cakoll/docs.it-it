---
title: Metodo ICLRRuntimeInfo::IsLoadable
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52257b30b8172b80f968df25115956b6995c1552
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101588"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="218ba-102">Metodo ICLRRuntimeInfo::IsLoadable</span><span class="sxs-lookup"><span data-stu-id="218ba-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="218ba-103">Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, prendendo in considerazione altri runtime che potrebbero essere già stato caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="218ba-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="218ba-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="218ba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="218ba-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="218ba-106">[out] `true` se questa istanza di runtime può essere caricato nel processo corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="218ba-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="218ba-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="218ba-107">Return Value</span></span>  
 <span data-ttu-id="218ba-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="218ba-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="218ba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="218ba-109">HRESULT</span></span>|<span data-ttu-id="218ba-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="218ba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="218ba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="218ba-111">S_OK</span></span>|<span data-ttu-id="218ba-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="218ba-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="218ba-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="218ba-113">E_POINTER</span></span>|<span data-ttu-id="218ba-114">`pbLoadable` è null.</span><span class="sxs-lookup"><span data-stu-id="218ba-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="218ba-115">Note</span><span class="sxs-lookup"><span data-stu-id="218ba-115">Remarks</span></span>  
 <span data-ttu-id="218ba-116">Se un altro runtime è già caricato nel processo e il runtime associato a questa interfaccia può essere caricato per l'esecuzione side-by-side in-process, `pbLoadable` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="218ba-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="218ba-117">Se non è possono eseguire i due runtime side-by-side in-process `pbLoadable` restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="218ba-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="218ba-118">Ad esempio, common language runtime (CLR) versione 4 è possibile eseguire side-by-side nello stesso processo con la versione 2.0 di CLR o CLR versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="218ba-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="218ba-119">Tuttavia, CLR versione 1.1 e 2.0 di CLR non è possibile eseguire side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="218ba-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="218ba-120">Se nessun runtime vengono caricati nel processo, questo metodo restituisce sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="218ba-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218ba-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="218ba-121">Requirements</span></span>  
 <span data-ttu-id="218ba-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="218ba-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="218ba-123">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="218ba-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="218ba-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="218ba-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="218ba-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="218ba-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218ba-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="218ba-126">See also</span></span>

- [<span data-ttu-id="218ba-127">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="218ba-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="218ba-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="218ba-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="218ba-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="218ba-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
