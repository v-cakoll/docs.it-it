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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101588"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="02050-102">Metodo ICLRRuntimeInfo::IsLoadable</span><span class="sxs-lookup"><span data-stu-id="02050-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="02050-103">Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, prendendo in considerazione altri runtime che potrebbero essere già stato caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="02050-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02050-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02050-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02050-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="02050-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="02050-106">[out] `true` se questa istanza di runtime può essere caricato nel processo corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="02050-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02050-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="02050-107">Return Value</span></span>  
 <span data-ttu-id="02050-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="02050-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="02050-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02050-109">HRESULT</span></span>|<span data-ttu-id="02050-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02050-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02050-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="02050-111">S_OK</span></span>|<span data-ttu-id="02050-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="02050-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="02050-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="02050-113">E_POINTER</span></span>|`pbLoadable` <span data-ttu-id="02050-114">è null.</span><span class="sxs-lookup"><span data-stu-id="02050-114">is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02050-115">Note</span><span class="sxs-lookup"><span data-stu-id="02050-115">Remarks</span></span>  
 <span data-ttu-id="02050-116">Se un altro runtime è già caricato nel processo e il runtime associato a questa interfaccia può essere caricato per l'esecuzione side-by-side in-process, `pbLoadable` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="02050-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="02050-117">Se non è possono eseguire i due runtime side-by-side in-process `pbLoadable` restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="02050-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="02050-118">Ad esempio, common language runtime (CLR) versione 4 è possibile eseguire side-by-side nello stesso processo con la versione 2.0 di CLR o CLR versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="02050-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="02050-119">Tuttavia, CLR versione 1.1 e 2.0 di CLR non è possibile eseguire side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="02050-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="02050-120">Se nessun runtime vengono caricati nel processo, questo metodo restituisce sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="02050-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02050-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02050-121">Requirements</span></span>  
 <span data-ttu-id="02050-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02050-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02050-123">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="02050-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="02050-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="02050-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="02050-125">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="02050-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="02050-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02050-126">See also</span></span>

- [<span data-ttu-id="02050-127">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="02050-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="02050-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="02050-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="02050-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="02050-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
