---
title: Metodo ICLRRuntimeInfo::GetInterface
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4244ef04d6789b7c17ccc8330cb0c26a6c9f3866
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765554"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="d8415-102">Metodo ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="d8415-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="d8415-103">Carica CLR nel processo corrente e restituisce come puntatori a interfaccia, runtime [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), e [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d8415-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="d8415-104">Questo metodo sostituisce tutte le `CorBindTo`\* funzioni nel [funzioni di Hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) sezione.</span><span class="sxs-lookup"><span data-stu-id="d8415-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8415-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8415-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8415-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8415-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="d8415-107">[in] L'interfaccia CLSID della coclasse.</span><span class="sxs-lookup"><span data-stu-id="d8415-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="d8415-108">[in] L'IID richiesti `rclsid` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d8415-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="d8415-109">[out] Un puntatore all'interfaccia di query.</span><span class="sxs-lookup"><span data-stu-id="d8415-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8415-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d8415-110">Return Value</span></span>  
 <span data-ttu-id="d8415-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="d8415-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d8415-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8415-112">HRESULT</span></span>|<span data-ttu-id="d8415-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8415-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8415-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8415-114">S_OK</span></span>|<span data-ttu-id="d8415-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d8415-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="d8415-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d8415-116">E_POINTER</span></span>|<span data-ttu-id="d8415-117">`ppUnk` è null.</span><span class="sxs-lookup"><span data-stu-id="d8415-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="d8415-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d8415-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d8415-119">Memoria insufficiente è disponibile per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="d8415-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="d8415-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="d8415-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="d8415-121">Un runtime diverso era già associato ai criteri di attivazione 2 versione CLR legacy.</span><span class="sxs-lookup"><span data-stu-id="d8415-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8415-122">Note</span><span class="sxs-lookup"><span data-stu-id="d8415-122">Remarks</span></span>  
 <span data-ttu-id="d8415-123">Questo metodo, il CLR caricato ma non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="d8415-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="d8415-124">La tabella seguente mostra le combinazioni supportate per `rclsid` e `riid`.</span><span class="sxs-lookup"><span data-stu-id="d8415-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="d8415-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="d8415-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="d8415-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d8415-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="d8415-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="d8415-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="d8415-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d8415-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="d8415-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d8415-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="d8415-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d8415-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="d8415-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d8415-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="d8415-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d8415-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="d8415-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="d8415-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="d8415-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="d8415-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="d8415-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="d8415-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="d8415-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="d8415-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="d8415-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d8415-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="d8415-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d8415-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8415-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8415-139">Requirements</span></span>  
 <span data-ttu-id="d8415-140">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8415-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8415-141">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d8415-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d8415-142">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d8415-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8415-143">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8415-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8415-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8415-144">See also</span></span>

- [<span data-ttu-id="d8415-145">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="d8415-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="d8415-146">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d8415-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d8415-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="d8415-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
