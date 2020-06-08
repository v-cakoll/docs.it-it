---
title: Metodo ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 45e27ac3c2d4912d2ed3e5d43ea3020b9db5dbdc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504030"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="4d438-102">Metodo ICLRRuntimeInfo::IsLoaded</span><span class="sxs-lookup"><span data-stu-id="4d438-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="4d438-103">Indica se il Common Language Runtime (CLR) associato all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) viene caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="4d438-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="4d438-104">È possibile caricare un runtime anche senza avviare.</span><span class="sxs-lookup"><span data-stu-id="4d438-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d438-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d438-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d438-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d438-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="4d438-107">in Handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="4d438-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="4d438-108">[out] `true` Se CLR viene caricato nel processo; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="4d438-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d438-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4d438-109">Return Value</span></span>  
 <span data-ttu-id="4d438-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4d438-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4d438-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d438-111">HRESULT</span></span>|<span data-ttu-id="4d438-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d438-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d438-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d438-113">S_OK</span></span>|<span data-ttu-id="4d438-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4d438-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="4d438-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4d438-115">E_POINTER</span></span>|<span data-ttu-id="4d438-116">`pbLoaded` è null.</span><span class="sxs-lookup"><span data-stu-id="4d438-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d438-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4d438-117">Remarks</span></span>  
 <span data-ttu-id="4d438-118">Questo metodo è compatibile con le versioni precedenti con le funzioni e le interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d438-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="4d438-119">Interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) (nell'API di hosting .NET Framework versione 1).</span><span class="sxs-lookup"><span data-stu-id="4d438-119">[ICorRuntimeHost](icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="4d438-120">Interfaccia [ICLRRuntimeHost](iclrruntimehost-interface.md) (nell'API di hosting .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="4d438-120">[ICLRRuntimeHost](iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="4d438-121">Funzioni deprecate `CorBindTo*` (vedere [funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md) nell'API di hosting .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="4d438-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="4d438-122">Un host può chiamare una delle funzioni deprecate `CorBindTo*` , ad esempio la funzione [CorBindToRuntime](corbindtoruntime-function.md) , per creare un'istanza di una specifica versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="4d438-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="4d438-123">L'host può quindi chiamare il metodo [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) e specificare lo stesso numero di versione per ottenere un'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4d438-123">The host could then call the [ICLRMetaHost::GetRuntime](iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="4d438-124">Se l'host chiama quindi il `IsLoaded` metodo sull'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) restituita, `pbLoaded` restituisce `true` ; in caso contrario, restituisce `false` .</span><span class="sxs-lookup"><span data-stu-id="4d438-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d438-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d438-125">Requirements</span></span>  
 <span data-ttu-id="4d438-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d438-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d438-127">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4d438-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4d438-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4d438-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d438-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d438-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d438-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d438-130">See also</span></span>

- [<span data-ttu-id="4d438-131">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="4d438-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="4d438-132">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4d438-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4d438-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="4d438-133">Hosting</span></span>](index.md)
