---
title: Funzione CorBindToRuntimeByCfg
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd7a1fd7bdd7e143ab89d509c4c70026d3f22c4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431864"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="c0f3e-102">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="c0f3e-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="c0f3e-103">Carica common language runtime (CLR) in un processo con informazioni sulla versione che viene letto da un file XML.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="c0f3e-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0f3e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f3e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0f3e-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0f3e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0f3e-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="c0f3e-107">[in] Un puntatore a un `IStream` oggetto che legge il file XML.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="c0f3e-108">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-108">[in] Reserved for future use.</span></span> <span data-ttu-id="c0f3e-109">Usare 0 (zero) come valore.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="c0f3e-110">[in] Il valore di [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumerazione che specifica il comportamento di avvio di CLR.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="c0f3e-111">[in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="c0f3e-112">Valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="c0f3e-113">[in] Il `IID` di uno il `ICorRuntimeHost` o `ICLRRuntimeHost` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="c0f3e-114">Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="c0f3e-115">[out] Un puntatore all'indirizzo dell'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0f3e-116">Note</span><span class="sxs-lookup"><span data-stu-id="c0f3e-116">Remarks</span></span>  
 <span data-ttu-id="c0f3e-117">Il formato del file XML viene modellato in file di configurazione dell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="c0f3e-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="c0f3e-118">Per ulteriori informazioni sui file XML, vedere [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0f3e-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f3e-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0f3e-119">Requirements</span></span>  
 <span data-ttu-id="c0f3e-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0f3e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0f3e-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c0f3e-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0f3e-122">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c0f3e-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0f3e-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0f3e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f3e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f3e-124">See Also</span></span>  
 [<span data-ttu-id="c0f3e-125">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="c0f3e-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="c0f3e-126">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="c0f3e-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="c0f3e-127">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="c0f3e-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="c0f3e-128">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c0f3e-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="c0f3e-129">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c0f3e-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="c0f3e-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="c0f3e-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
