---
title: Metodo ICLRMetaHost::QueryLegacyV2RuntimeBinding
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: 90474a61b16d65565889bd69ef75616804d8bc60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140877"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="8d234-102">Metodo ICLRMetaHost::QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="8d234-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="8d234-103">Restituisce un'interfaccia che rappresenta un runtime a cui sono stati associati i criteri di attivazione legacy, ad esempio usando l'attributo `useLegacyV2RuntimeActivationPolicy` nella voce [\<startup >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) file di configurazione dell'elemento, dall'uso diretto delle API di attivazione legacy o chiamando il metodo [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8d234-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d234-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d234-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d234-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d234-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="8d234-106">in Obbligatorio. attualmente l'unico valore valido per questo parametro è `IID_ICLRRuntimeInfo`.</span><span class="sxs-lookup"><span data-stu-id="8d234-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="8d234-107">[out] Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d234-107">[out] Required.</span></span> <span data-ttu-id="8d234-108">Quando termina, questo metodo contiene un puntatore all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) che rappresenta un runtime che è stato associato ai criteri di attivazione legacy.</span><span class="sxs-lookup"><span data-stu-id="8d234-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d234-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8d234-109">Return Value</span></span>  
 <span data-ttu-id="8d234-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="8d234-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8d234-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d234-111">HRESULT</span></span>|<span data-ttu-id="8d234-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d234-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d234-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d234-113">S_OK</span></span>|<span data-ttu-id="8d234-114">Il metodo ha completato correttamente e restituito un runtime che era associato ai criteri dell'attivazione legacy.</span><span class="sxs-lookup"><span data-stu-id="8d234-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="8d234-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8d234-115">S_FALSE</span></span>|<span data-ttu-id="8d234-116">Il metodo ha completato correttamente, ma un runtime legacy non è stato ancora associato.</span><span class="sxs-lookup"><span data-stu-id="8d234-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="8d234-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="8d234-117">E_NOINTERFACE</span></span>|<span data-ttu-id="8d234-118">Il metodo ha trovato un runtime associato ai criteri dell'attivazione legacy, ma `riid` non è supportato da quel runtime.</span><span class="sxs-lookup"><span data-stu-id="8d234-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d234-119">Note</span><span class="sxs-lookup"><span data-stu-id="8d234-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d234-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d234-120">Requirements</span></span>  
 <span data-ttu-id="8d234-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d234-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d234-122">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="8d234-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8d234-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8d234-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d234-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d234-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d234-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d234-125">See also</span></span>

- [<span data-ttu-id="8d234-126">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="8d234-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="8d234-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="8d234-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
