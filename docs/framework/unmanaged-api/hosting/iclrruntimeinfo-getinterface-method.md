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
ms.openlocfilehash: c8ac959c192814562488ab916c8462b0baa0d8e6
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703642"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="898c5-102">Metodo ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="898c5-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="898c5-103">Carica CLR nel processo corrente e restituisce i puntatori dell'interfaccia di runtime, ad esempio [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)e [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="898c5-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="898c5-104">Questo metodo sostituisce tutte le `CorBindTo` funzioni \* nella sezione [funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="898c5-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898c5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="898c5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="898c5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="898c5-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="898c5-107">in Interfaccia CLSID per la coclasse.</span><span class="sxs-lookup"><span data-stu-id="898c5-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="898c5-108">in IID dell' `rclsid` interfaccia richiesta.</span><span class="sxs-lookup"><span data-stu-id="898c5-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="898c5-109">out Puntatore all'interfaccia sottoposta a query.</span><span class="sxs-lookup"><span data-stu-id="898c5-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="898c5-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="898c5-110">Return Value</span></span>  
 <span data-ttu-id="898c5-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="898c5-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="898c5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="898c5-112">HRESULT</span></span>|<span data-ttu-id="898c5-113">Description</span><span class="sxs-lookup"><span data-stu-id="898c5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="898c5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="898c5-114">S_OK</span></span>|<span data-ttu-id="898c5-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="898c5-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="898c5-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="898c5-116">E_POINTER</span></span>|<span data-ttu-id="898c5-117">`ppUnk` è null.</span><span class="sxs-lookup"><span data-stu-id="898c5-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="898c5-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="898c5-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="898c5-119">La memoria disponibile non è sufficiente per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="898c5-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="898c5-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="898c5-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="898c5-121">Un runtime diverso era già associato ai criteri di attivazione di CLR versione 2 Legacy.</span><span class="sxs-lookup"><span data-stu-id="898c5-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="898c5-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="898c5-122">Remarks</span></span>  
 <span data-ttu-id="898c5-123">Questo metodo fa sì che CLR venga caricato ma non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="898c5-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="898c5-124">Nella tabella seguente vengono illustrate le combinazioni supportate per `rclsid` e `riid` .</span><span class="sxs-lookup"><span data-stu-id="898c5-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="898c5-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="898c5-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="898c5-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="898c5-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="898c5-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="898c5-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="898c5-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="898c5-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="898c5-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="898c5-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="898c5-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="898c5-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="898c5-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="898c5-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="898c5-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="898c5-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="898c5-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="898c5-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="898c5-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="898c5-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="898c5-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="898c5-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="898c5-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="898c5-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="898c5-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="898c5-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="898c5-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="898c5-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="898c5-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="898c5-139">Requirements</span></span>  
 <span data-ttu-id="898c5-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="898c5-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898c5-141">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="898c5-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="898c5-142">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="898c5-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="898c5-143">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898c5-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898c5-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="898c5-144">See also</span></span>

- [<span data-ttu-id="898c5-145">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="898c5-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="898c5-146">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="898c5-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="898c5-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="898c5-147">Hosting</span></span>](index.md)
