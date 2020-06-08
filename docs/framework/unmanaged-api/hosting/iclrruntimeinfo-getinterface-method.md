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
ms.openlocfilehash: 9cf9d48bf50ffc1fc56270c13215acfef6d9c3af
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504056"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="c1cf2-102">Metodo ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="c1cf2-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="c1cf2-103">Carica CLR nel processo corrente e restituisce i puntatori dell'interfaccia di runtime, ad esempio [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)e [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c1cf2-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="c1cf2-104">Questo metodo sostituisce tutte le `CorBindTo` funzioni \* nella sezione [funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="c1cf2-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1cf2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1cf2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1cf2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1cf2-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="c1cf2-107">in Interfaccia CLSID per la coclasse.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="c1cf2-108">in IID dell' `rclsid` interfaccia richiesta.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="c1cf2-109">out Puntatore all'interfaccia sottoposta a query.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1cf2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c1cf2-110">Return Value</span></span>  
 <span data-ttu-id="c1cf2-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c1cf2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1cf2-112">HRESULT</span></span>|<span data-ttu-id="c1cf2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1cf2-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1cf2-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1cf2-114">S_OK</span></span>|<span data-ttu-id="c1cf2-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="c1cf2-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c1cf2-116">E_POINTER</span></span>|<span data-ttu-id="c1cf2-117">`ppUnk` è null.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="c1cf2-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c1cf2-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c1cf2-119">La memoria disponibile non è sufficiente per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="c1cf2-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="c1cf2-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="c1cf2-121">Un runtime diverso era già associato ai criteri di attivazione di CLR versione 2 Legacy.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1cf2-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c1cf2-122">Remarks</span></span>  
 <span data-ttu-id="c1cf2-123">Questo metodo fa sì che CLR venga caricato ma non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="c1cf2-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="c1cf2-124">Nella tabella seguente vengono illustrate le combinazioni supportate per `rclsid` e `riid` .</span><span class="sxs-lookup"><span data-stu-id="c1cf2-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="c1cf2-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="c1cf2-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="c1cf2-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="c1cf2-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="c1cf2-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="c1cf2-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="c1cf2-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="c1cf2-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="c1cf2-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c1cf2-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="c1cf2-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c1cf2-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="c1cf2-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c1cf2-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="c1cf2-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c1cf2-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="c1cf2-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="c1cf2-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="c1cf2-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="c1cf2-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="c1cf2-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="c1cf2-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="c1cf2-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c1cf2-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="c1cf2-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c1cf2-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="c1cf2-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c1cf2-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1cf2-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1cf2-139">Requirements</span></span>  
 <span data-ttu-id="c1cf2-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1cf2-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1cf2-141">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="c1cf2-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c1cf2-142">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c1cf2-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1cf2-143">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1cf2-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1cf2-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1cf2-144">See also</span></span>

- [<span data-ttu-id="c1cf2-145">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="c1cf2-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c1cf2-146">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c1cf2-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="c1cf2-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="c1cf2-147">Hosting</span></span>](index.md)
