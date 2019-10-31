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
ms.openlocfilehash: 295deeec2e8eb42ccaa4d0cfb8b08b32438d047c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120245"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="9746c-102">Metodo ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="9746c-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="9746c-103">Carica CLR nel processo corrente e restituisce i puntatori dell'interfaccia di runtime, ad esempio [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)e [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9746c-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="9746c-104">Questo metodo sostituisce tutte le funzioni `CorBindTo`\* nella sezione [funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="9746c-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9746c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9746c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9746c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9746c-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="9746c-107">in Interfaccia CLSID per la coclasse.</span><span class="sxs-lookup"><span data-stu-id="9746c-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="9746c-108">in IID dell'interfaccia `rclsid` richiesta.</span><span class="sxs-lookup"><span data-stu-id="9746c-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="9746c-109">out Puntatore all'interfaccia sottoposta a query.</span><span class="sxs-lookup"><span data-stu-id="9746c-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9746c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9746c-110">Return Value</span></span>  
 <span data-ttu-id="9746c-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9746c-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9746c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9746c-112">HRESULT</span></span>|<span data-ttu-id="9746c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9746c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9746c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9746c-114">S_OK</span></span>|<span data-ttu-id="9746c-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9746c-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="9746c-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9746c-116">E_POINTER</span></span>|<span data-ttu-id="9746c-117">`ppUnk` è null.</span><span class="sxs-lookup"><span data-stu-id="9746c-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="9746c-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9746c-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9746c-119">La memoria disponibile non è sufficiente per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="9746c-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="9746c-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="9746c-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="9746c-121">Un runtime diverso era già associato ai criteri di attivazione di CLR versione 2 Legacy.</span><span class="sxs-lookup"><span data-stu-id="9746c-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9746c-122">Note</span><span class="sxs-lookup"><span data-stu-id="9746c-122">Remarks</span></span>  
 <span data-ttu-id="9746c-123">Questo metodo fa sì che CLR venga caricato ma non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="9746c-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="9746c-124">Nella tabella seguente vengono illustrate le combinazioni supportate per `rclsid` e `riid`.</span><span class="sxs-lookup"><span data-stu-id="9746c-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="9746c-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="9746c-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="9746c-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="9746c-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="9746c-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="9746c-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="9746c-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="9746c-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="9746c-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9746c-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="9746c-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9746c-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="9746c-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9746c-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="9746c-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9746c-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="9746c-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="9746c-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="9746c-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="9746c-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="9746c-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="9746c-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="9746c-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="9746c-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="9746c-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9746c-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="9746c-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9746c-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9746c-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9746c-139">Requirements</span></span>  
 <span data-ttu-id="9746c-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9746c-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9746c-141">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9746c-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9746c-142">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9746c-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9746c-143">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9746c-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9746c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9746c-144">See also</span></span>

- [<span data-ttu-id="9746c-145">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="9746c-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="9746c-146">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9746c-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9746c-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="9746c-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
