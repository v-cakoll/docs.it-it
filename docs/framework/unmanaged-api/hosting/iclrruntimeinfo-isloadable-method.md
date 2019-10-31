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
ms.openlocfilehash: 9339bb974c261e62502c760dfaf45651573cbe1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136367"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="22cc7-102">Metodo ICLRRuntimeInfo::IsLoadable</span><span class="sxs-lookup"><span data-stu-id="22cc7-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="22cc7-103">Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, tenendo conto di altri runtime che potrebbero essere già stati caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="22cc7-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22cc7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22cc7-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22cc7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22cc7-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="22cc7-106">[out] `true` se il runtime può essere caricato nel processo corrente; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="22cc7-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22cc7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22cc7-107">Return Value</span></span>  
 <span data-ttu-id="22cc7-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="22cc7-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="22cc7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22cc7-109">HRESULT</span></span>|<span data-ttu-id="22cc7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22cc7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22cc7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="22cc7-111">S_OK</span></span>|<span data-ttu-id="22cc7-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="22cc7-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="22cc7-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="22cc7-113">E_POINTER</span></span>|<span data-ttu-id="22cc7-114">`pbLoadable` è null.</span><span class="sxs-lookup"><span data-stu-id="22cc7-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22cc7-115">Note</span><span class="sxs-lookup"><span data-stu-id="22cc7-115">Remarks</span></span>  
 <span data-ttu-id="22cc7-116">Se un altro runtime è già caricato nel processo e il runtime associato a questa interfaccia può essere caricato per l'esecuzione side-by-side in-process, `pbLoadable` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="22cc7-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="22cc7-117">Se i due runtime non possono essere eseguiti side-by-side in-process, `pbLoadable` restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="22cc7-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="22cc7-118">Ad esempio, il Common Language Runtime (CLR) versione 4 può essere eseguito side-by-side nello stesso processo con CLR versione 2,0 o CLR versione 1,1.</span><span class="sxs-lookup"><span data-stu-id="22cc7-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="22cc7-119">Tuttavia, la versione CLR 1,1 e la versione 2,0 CLR non possono essere eseguite side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="22cc7-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="22cc7-120">Se nel processo non sono stati caricati Runtime, questo metodo restituisce sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="22cc7-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22cc7-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22cc7-121">Requirements</span></span>  
 <span data-ttu-id="22cc7-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22cc7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22cc7-123">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="22cc7-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="22cc7-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22cc7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22cc7-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22cc7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22cc7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22cc7-126">See also</span></span>

- [<span data-ttu-id="22cc7-127">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="22cc7-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="22cc7-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="22cc7-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="22cc7-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="22cc7-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
