---
title: Funzione CorBindToRuntimeByCfg
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeByCfg
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeByCfg
helpviewer_keywords: CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbf5a486246d1fb596c08f1510e6d5d89b03df62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="64f79-102">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="64f79-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="64f79-103">Carica common language runtime (CLR) in un processo con informazioni sulla versione che viene letto da un file XML.</span><span class="sxs-lookup"><span data-stu-id="64f79-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="64f79-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64f79-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f79-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64f79-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="64f79-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="64f79-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="64f79-107">[in] Un puntatore a un `IStream` oggetto che legge il file XML.</span><span class="sxs-lookup"><span data-stu-id="64f79-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="64f79-108">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="64f79-108">[in] Reserved for future use.</span></span> <span data-ttu-id="64f79-109">Usare 0 (zero) come valore.</span><span class="sxs-lookup"><span data-stu-id="64f79-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="64f79-110">[in] Il valore di [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumerazione che specifica il comportamento di avvio di CLR.</span><span class="sxs-lookup"><span data-stu-id="64f79-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="64f79-111">[in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="64f79-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="64f79-112">Valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="64f79-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="64f79-113">[in] Il `IID` di uno il `ICorRuntimeHost` o `ICLRRuntimeHost` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="64f79-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="64f79-114">Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="64f79-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="64f79-115">[out] Un puntatore all'indirizzo dell'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="64f79-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64f79-116">Note</span><span class="sxs-lookup"><span data-stu-id="64f79-116">Remarks</span></span>  
 <span data-ttu-id="64f79-117">Il formato del file XML viene modellato in file di configurazione dell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="64f79-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="64f79-118">Per ulteriori informazioni sui file XML, vedere [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="64f79-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64f79-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64f79-119">Requirements</span></span>  
 <span data-ttu-id="64f79-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64f79-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64f79-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="64f79-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64f79-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64f79-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64f79-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64f79-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f79-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64f79-124">See Also</span></span>  
 [<span data-ttu-id="64f79-125">CorBindToCurrentRuntime (funzione)</span><span class="sxs-lookup"><span data-stu-id="64f79-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="64f79-126">CorBindToRuntime (funzione)</span><span class="sxs-lookup"><span data-stu-id="64f79-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="64f79-127">CorBindToRuntimeEx (funzione)</span><span class="sxs-lookup"><span data-stu-id="64f79-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="64f79-128">CorBindToRuntimeHost (funzione)</span><span class="sxs-lookup"><span data-stu-id="64f79-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="64f79-129">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="64f79-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="64f79-130">Funzioni di Hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="64f79-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
