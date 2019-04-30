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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0252f27f30c3ce8abe349a2ddc45b20692fbb5ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993187"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="27165-102">Metodo ICLRMetaHost::QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="27165-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="27165-103">Restituisce un'interfaccia che rappresenta un runtime a cui sono stati associati i criteri dell'attivazione legacy, ad esempio, utilizzando il `useLegacyV2RuntimeActivationPolicy` attributo la [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) voce file di configurazione mediante l'utilizzo diretto dell'API di attivazione legacy o chiamando il [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="27165-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27165-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27165-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27165-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="27165-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="27165-106">[in] L'unico valore valido per questo parametro è Required.Currently `IID_ICLRRuntimeInfo`.</span><span class="sxs-lookup"><span data-stu-id="27165-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="27165-107">[out] Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="27165-107">[out] Required.</span></span> <span data-ttu-id="27165-108">Quando termina, questo metodo contiene un puntatore per il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia che rappresenta un runtime che è stato associato ai criteri dell'attivazione legacy.</span><span class="sxs-lookup"><span data-stu-id="27165-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27165-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="27165-109">Return Value</span></span>  
 <span data-ttu-id="27165-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="27165-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="27165-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27165-111">HRESULT</span></span>|<span data-ttu-id="27165-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27165-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27165-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="27165-113">S_OK</span></span>|<span data-ttu-id="27165-114">Il metodo ha completato correttamente e restituito un runtime che era associato ai criteri dell'attivazione legacy.</span><span class="sxs-lookup"><span data-stu-id="27165-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="27165-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="27165-115">S_FALSE</span></span>|<span data-ttu-id="27165-116">Il metodo ha completato correttamente, ma un runtime legacy non è stato ancora associato.</span><span class="sxs-lookup"><span data-stu-id="27165-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="27165-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="27165-117">E_NOINTERFACE</span></span>|<span data-ttu-id="27165-118">Il metodo ha trovato un runtime associato ai criteri dell'attivazione legacy, ma `riid` non è supportato da quel runtime.</span><span class="sxs-lookup"><span data-stu-id="27165-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27165-119">Note</span><span class="sxs-lookup"><span data-stu-id="27165-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27165-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27165-120">Requirements</span></span>  
 <span data-ttu-id="27165-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27165-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27165-122">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="27165-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="27165-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="27165-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27165-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27165-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27165-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27165-125">See also</span></span>

- [<span data-ttu-id="27165-126">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="27165-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="27165-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="27165-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
