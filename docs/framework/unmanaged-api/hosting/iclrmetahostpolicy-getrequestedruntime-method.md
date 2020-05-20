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
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>Metodo ICLRMetaHostPolicy::GetRequestedRuntime

Fornisce un'interfaccia a una versione preferita di Common Language Runtime (CLR) in base a criteri di hosting, un assembly gestito, una stringa di versione e un flusso di configurazione. Questo metodo non carica effettivamente o attiva CLR, ma restituisce semplicemente l'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) che rappresenta il risultato del criterio. Questo metodo sostituisce i metodi [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)e [GetCORRequiredVersion](getcorrequiredversion-function.md) .

## <a name="syntax"></a>Sintassi

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

## <a name="parameters"></a>Parametri

|Nome|Description|
|----------|-----------------|
|`dwPolicyFlags`|[in] Obbligatorio. Specifica un membro dell'enumerazione [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) , che rappresenta i criteri di associazione e qualsiasi numero di modificatori. L'unico criterio attualmente disponibile è [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).<br /><br /> I modificatori includono [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md)e [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).|
|`pwzBinary`|[in] Facoltativo. Specifica il percorso del file di assembly.|
|`pCfgStream`|[in] Facoltativo. Specifica il file di configurazione come oggetto <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|
|`pwzVersion`|[in, out] Facoltativo. Specifica o restituisce la versione di CLR preferita da caricare.|
|`pcchVersion`|[in, out] Obbligatorio. Specifica la dimensione prevista di `pwzVersion` come input per evitare sovraccarichi del buffer. Se `pwzVersion` è null, `pcchVersion` contiene le dimensioni previste di `pwzVersion` quando `GetRequestedRuntime` restituisce un valore, per consentire la preallocazione. In caso contrario, `pcchVersion` contiene il numero di caratteri scritti in `pwzVersion`.|
|`pwzImageVersion`|[out] Facoltativo. Quando `GetRequestedRuntime` viene restituito, contiene la versione CLR corrispondente all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) restituita.|
|`pcchImageVersion`|[in, out] Facoltativo. Specifica la dimensione di `pwzImageVersion` come input per evitare sovraccarichi del buffer. Se `pwzImageVersion` è null, `pcchImageVersion` contiene la dimensione richiesta di `pwzImageVersion` quando viene restituito `GetRequestedRuntime`, per consentire la preallocazione.|
|`pdwConfigFlags`|[out] Facoltativo. Se `GetRequestedRuntime` Usa un file di configurazione durante il processo di associazione, quando restituisce, `pdwConfigFlags` contiene un valore [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) che indica se l'elemento [ \<>di avvio](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) ha l' `useLegacyV2RuntimeActivationPolicy` attributo impostato e il valore dell'attributo. Applicare la maschera di [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) a `pdwConfigFlags` per ottenere i valori rilevanti per `useLegacyV2RuntimeActivationPolicy` .|
|`riid`|in Specifica l'identificatore di interfaccia IID_ICLRRuntimeInfo per l'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) richiesta.|
|`ppRuntime`|out Quando `GetRequestedRuntime` restituisce un valore, contiene un puntatore all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) corrispondente.|

## <a name="remarks"></a>Osservazioni

Quando questo metodo ha esito positivo presenta l'effetto collaterale di combinare flag aggiuntivi con i flag di avvio predefiniti correnti dell'interfaccia di runtime restituita, se e solo se uno o più degli elementi seguenti esiste nel flusso di configurazione all'interno della sezione `<configuration><runtime>`:

- `<gcServer enabled="true"/>` comporta l'impostazione di `STARTUP_SERVER_GC`.

- `<etwEnable enabled="true"/>` comporta l'impostazione di `STARTUP_ETW`.

- `<appDomainResourceMonitoring enabled="true"/>` comporta l'impostazione di `STARTUP_ARM`.

Il valore `STARTUP_FLAGS` predefinito risultante è la combinazione OR bit per bit dei valori che vengono impostati dall'elenco precedente con i flag di avvio predefiniti.

## <a name="return-value"></a>Valore restituito

Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.

|HRESULT|Description|
|-------------|-----------------|
|S_OK|Metodo completato correttamente.|
|E_POINTER|`pwzVersion` non è null e `pcchVersion` è null.<br /><br /> -oppure-<br /><br /> `pwzImageVersion` non è null e `pcchImageVersion` è null.|
|E_INVALIDARG|`dwPolicyFlags` non specifica `METAHOST_POLICY_HIGHCOMPAT`.|
|ERROR_INSUFFICIENT_BUFFER|La memoria allocata a `pwzVersion` è inadeguata.<br /><br /> -oppure-<br /><br /> La memoria allocata a `pwzImageVersion` è inadeguata.|
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags` include METAHOST_POLICY_APPLY_UPGRADE_POLICY e `pwzVersion` e `pcchVersion` sono null.|

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** Metahost. h

**Libreria:** Incluso come risorsa in MSCorEE. dll

**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)
- [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
