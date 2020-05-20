---
title: Metodo ICLRMetaHostPolicy::GetRequestedRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
ms.openlocfilehash: 52da5ec7ccd6ce48871e13a94f5957fa00d2a613
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703545"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a><span data-ttu-id="854a3-102">Metodo ICLRMetaHostPolicy::GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="854a3-102">ICLRMetaHostPolicy::GetRequestedRuntime Method</span></span>

<span data-ttu-id="854a3-103">Fornisce un'interfaccia a una versione preferita di Common Language Runtime (CLR) in base a criteri di hosting, un assembly gestito, una stringa di versione e un flusso di configurazione.</span><span class="sxs-lookup"><span data-stu-id="854a3-103">Provides an interface to a preferred version of the common language runtime (CLR) based on a hosting policy, managed assembly, version string, and configuration stream.</span></span> <span data-ttu-id="854a3-104">Questo metodo non carica effettivamente o attiva CLR, ma restituisce semplicemente l'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) che rappresenta il risultato del criterio.</span><span class="sxs-lookup"><span data-stu-id="854a3-104">This method does not actually load or activate the CLR, but simply returns the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents the policy result.</span></span> <span data-ttu-id="854a3-105">Questo metodo sostituisce i metodi [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)e [GetCORRequiredVersion](getcorrequiredversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="854a3-105">This method supersedes the [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), and [GetCORRequiredVersion](getcorrequiredversion-function.md) methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="854a3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="854a3-106">Syntax</span></span>

```cpp
HRESULT GetRequestedRuntime(
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,
    [in]  LPCWSTR pwzBinary,
    [in]  IStream *pCfgStream,
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,
    [in, out]  DWORD *pcchVersion,
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,
    [in, out]  DWORD *pcchImageVersion,
    [out] DWORD *pdwConfigFlags,
    [in]  REFIID  riid
    [out, iid_is(riid), retval] LPVOID *ppRuntime);
```

## <a name="parameters"></a><span data-ttu-id="854a3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="854a3-107">Parameters</span></span>

|<span data-ttu-id="854a3-108">Nome</span><span class="sxs-lookup"><span data-stu-id="854a3-108">Name</span></span>|<span data-ttu-id="854a3-109">Description</span><span class="sxs-lookup"><span data-stu-id="854a3-109">Description</span></span>|
|----------|-----------------|
|`dwPolicyFlags`|<span data-ttu-id="854a3-110">[in] Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="854a3-110">[in] Required.</span></span> <span data-ttu-id="854a3-111">Specifica un membro dell'enumerazione [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) , che rappresenta i criteri di associazione e qualsiasi numero di modificatori.</span><span class="sxs-lookup"><span data-stu-id="854a3-111">Specifies a member of the [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration, representing a binding policy, and any number of modifiers.</span></span> <span data-ttu-id="854a3-112">L'unico criterio attualmente disponibile è [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="854a3-112">The only policy that is currently available is [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).</span></span><br /><br /> <span data-ttu-id="854a3-113">I modificatori includono [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md)e [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="854a3-113">Modifiers include [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md), and [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).</span></span>|
|`pwzBinary`|<span data-ttu-id="854a3-114">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="854a3-114">[in] Optional.</span></span> <span data-ttu-id="854a3-115">Specifica il percorso del file di assembly.</span><span class="sxs-lookup"><span data-stu-id="854a3-115">Specifies the assembly file path.</span></span>|
|`pCfgStream`|<span data-ttu-id="854a3-116">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="854a3-116">[in] Optional.</span></span> <span data-ttu-id="854a3-117">Specifica il file di configurazione come oggetto <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="854a3-117">Specifies the configuration file as a <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span></span>|
|`pwzVersion`|<span data-ttu-id="854a3-118">[in, out] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="854a3-118">[in, out] Optional.</span></span> <span data-ttu-id="854a3-119">Specifica o restituisce la versione di CLR preferita da caricare.</span><span class="sxs-lookup"><span data-stu-id="854a3-119">Specifies or returns the preferred CLR version to be loaded.</span></span>|
|`pcchVersion`|<span data-ttu-id="854a3-120">[in, out] Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="854a3-120">[in, out] Required.</span></span> <span data-ttu-id="854a3-121">Specifica la dimensione prevista di `pwzVersion` come input per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="854a3-121">Specifies the expected size of `pwzVersion` as input, to avoid buffer overruns.</span></span> <span data-ttu-id="854a3-122">Se `pwzVersion` è null, `pcchVersion` contiene le dimensioni previste di `pwzVersion` quando `GetRequestedRuntime` restituisce un valore, per consentire la preallocazione. In caso contrario, `pcchVersion` contiene il numero di caratteri scritti in `pwzVersion`.</span><span class="sxs-lookup"><span data-stu-id="854a3-122">If `pwzVersion` is null, `pcchVersion` contains the expected size of `pwzVersion` when `GetRequestedRuntime` returns, to allow pre-allocation; otherwise, `pcchVersion` contains the number of characters written to `pwzVersion`.</span></span>|
|`pwzImageVersion`|<span data-ttu-id="854a3-123">[out] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="854a3-123">[out] Optional.</span></span> <span data-ttu-id="854a3-124">Quando `GetRequestedRuntime` viene restituito, contiene la versione CLR corrispondente all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="854a3-124">When `GetRequestedRuntime` returns, contains the CLR version corresponding to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that is returned.</span></span>|
|`pcchImageVersion`|<span data-ttu-id="854a3-125">[in, out] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="854a3-125">[in, out] Optional.</span></span> <span data-ttu-id="854a3-126">Specifica la dimensione di `pwzImageVersion` come input per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="854a3-126">Specifies the size of `pwzImageVersion` as input to avoid buffer overruns.</span></span> <span data-ttu-id="854a3-127">Se `pwzImageVersion` è null, `pcchImageVersion` contiene la dimensione richiesta di `pwzImageVersion` quando viene restituito `GetRequestedRuntime`, per consentire la preallocazione.</span><span class="sxs-lookup"><span data-stu-id="854a3-127">If `pwzImageVersion` is null, `pcchImageVersion` contains the required size of `pwzImageVersion` when `GetRequestedRuntime` returns, to allow pre-allocation.</span></span>|
|`pdwConfigFlags`|<span data-ttu-id="854a3-128">[out] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="854a3-128">[out] Optional.</span></span> <span data-ttu-id="854a3-129">Se `GetRequestedRuntime` Usa un file di configurazione durante il processo di associazione, quando restituisce, `pdwConfigFlags` contiene un valore [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) che indica se l'elemento [ \<>di avvio](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) ha l' `useLegacyV2RuntimeActivationPolicy` attributo impostato e il valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="854a3-129">If `GetRequestedRuntime` uses a configuration file during the binding process, when it returns, `pdwConfigFlags` contains a [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) value that indicates whether the [\<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) element has the `useLegacyV2RuntimeActivationPolicy` attribute set, and the value of the attribute.</span></span> <span data-ttu-id="854a3-130">Applicare la maschera di [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) a `pdwConfigFlags` per ottenere i valori rilevanti per `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="854a3-130">Apply the [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) mask to `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|
|`riid`|<span data-ttu-id="854a3-131">in Specifica l'identificatore di interfaccia IID_ICLRRuntimeInfo per l'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) richiesta.</span><span class="sxs-lookup"><span data-stu-id="854a3-131">[in] Specifies the interface identifier IID_ICLRRuntimeInfo for the requested [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|
|`ppRuntime`|<span data-ttu-id="854a3-132">out Quando `GetRequestedRuntime` restituisce un valore, contiene un puntatore all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="854a3-132">[out] When `GetRequestedRuntime` returns, contains a pointer to the corresponding [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|

## <a name="remarks"></a><span data-ttu-id="854a3-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="854a3-133">Remarks</span></span>

<span data-ttu-id="854a3-134">Quando questo metodo ha esito positivo presenta l'effetto collaterale di combinare flag aggiuntivi con i flag di avvio predefiniti correnti dell'interfaccia di runtime restituita, se e solo se uno o più degli elementi seguenti esiste nel flusso di configurazione all'interno della sezione `<configuration><runtime>`:</span><span class="sxs-lookup"><span data-stu-id="854a3-134">When this method succeeds, it has the side effect of combining additional flags with the current default startup flags of the returned runtime interface, if and only if one or more of the following elements exist in the configuration stream within the `<configuration><runtime>` section:</span></span>

- <span data-ttu-id="854a3-135">`<gcServer enabled="true"/>` comporta l'impostazione di `STARTUP_SERVER_GC`.</span><span class="sxs-lookup"><span data-stu-id="854a3-135">`<gcServer enabled="true"/>` causes `STARTUP_SERVER_GC` to be set.</span></span>

- <span data-ttu-id="854a3-136">`<etwEnable enabled="true"/>` comporta l'impostazione di `STARTUP_ETW`.</span><span class="sxs-lookup"><span data-stu-id="854a3-136">`<etwEnable enabled="true"/>` causes `STARTUP_ETW` to be set.</span></span>

- <span data-ttu-id="854a3-137">`<appDomainResourceMonitoring enabled="true"/>` comporta l'impostazione di `STARTUP_ARM`.</span><span class="sxs-lookup"><span data-stu-id="854a3-137">`<appDomainResourceMonitoring enabled="true"/>` causes `STARTUP_ARM` to be set.</span></span>

<span data-ttu-id="854a3-138">Il valore `STARTUP_FLAGS` predefinito risultante è la combinazione OR bit per bit dei valori che vengono impostati dall'elenco precedente con i flag di avvio predefiniti.</span><span class="sxs-lookup"><span data-stu-id="854a3-138">The resulting default `STARTUP_FLAGS` value is the bitwise OR combination of the values that are set from the preceding list with the default startup flags.</span></span>

## <a name="return-value"></a><span data-ttu-id="854a3-139">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="854a3-139">Return Value</span></span>

<span data-ttu-id="854a3-140">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="854a3-140">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="854a3-141">HRESULT</span><span class="sxs-lookup"><span data-stu-id="854a3-141">HRESULT</span></span>|<span data-ttu-id="854a3-142">Description</span><span class="sxs-lookup"><span data-stu-id="854a3-142">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="854a3-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="854a3-143">S_OK</span></span>|<span data-ttu-id="854a3-144">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="854a3-144">The method completed successfully.</span></span>|
|<span data-ttu-id="854a3-145">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="854a3-145">E_POINTER</span></span>|<span data-ttu-id="854a3-146">`pwzVersion` non è null e `pcchVersion` è null.</span><span class="sxs-lookup"><span data-stu-id="854a3-146">`pwzVersion` is not null and `pcchVersion` is null.</span></span><br /><br /> <span data-ttu-id="854a3-147">-oppure-</span><span class="sxs-lookup"><span data-stu-id="854a3-147">-or-</span></span><br /><br /> <span data-ttu-id="854a3-148">`pwzImageVersion` non è null e `pcchImageVersion` è null.</span><span class="sxs-lookup"><span data-stu-id="854a3-148">`pwzImageVersion` is not null and `pcchImageVersion` is null.</span></span>|
|<span data-ttu-id="854a3-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="854a3-149">E_INVALIDARG</span></span>|<span data-ttu-id="854a3-150">`dwPolicyFlags` non specifica `METAHOST_POLICY_HIGHCOMPAT`.</span><span class="sxs-lookup"><span data-stu-id="854a3-150">`dwPolicyFlags` does not specify `METAHOST_POLICY_HIGHCOMPAT`.</span></span>|
|<span data-ttu-id="854a3-151">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="854a3-151">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="854a3-152">La memoria allocata a `pwzVersion` è inadeguata.</span><span class="sxs-lookup"><span data-stu-id="854a3-152">The memory allocated to `pwzVersion` is inadequate.</span></span><br /><br /> <span data-ttu-id="854a3-153">-oppure-</span><span class="sxs-lookup"><span data-stu-id="854a3-153">-or-</span></span><br /><br /> <span data-ttu-id="854a3-154">La memoria allocata a `pwzImageVersion` è inadeguata.</span><span class="sxs-lookup"><span data-stu-id="854a3-154">The memory allocated to `pwzImageVersion` is inadequate.</span></span>|
|<span data-ttu-id="854a3-155">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="854a3-155">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="854a3-156">`dwPolicyFlags` include METAHOST_POLICY_APPLY_UPGRADE_POLICY e `pwzVersion` e `pcchVersion` sono null.</span><span class="sxs-lookup"><span data-stu-id="854a3-156">`dwPolicyFlags` includes METAHOST_POLICY_APPLY_UPGRADE_POLICY, and both `pwzVersion` and `pcchVersion` are null.</span></span>|

## <a name="requirements"></a><span data-ttu-id="854a3-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="854a3-157">Requirements</span></span>

<span data-ttu-id="854a3-158">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="854a3-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="854a3-159">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="854a3-159">**Header:** MetaHost.h</span></span>

<span data-ttu-id="854a3-160">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="854a3-160">**Library:** Included as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="854a3-161">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="854a3-161">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="854a3-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="854a3-162">See also</span></span>

- [<span data-ttu-id="854a3-163">Interfaccia ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="854a3-163">ICLRMetaHostPolicy Interface</span></span>](iclrmetahostpolicy-interface.md)
- [<span data-ttu-id="854a3-164">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="854a3-164">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="854a3-165">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="854a3-165">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="854a3-166">Hosting</span><span class="sxs-lookup"><span data-stu-id="854a3-166">Hosting</span></span>](index.md)
