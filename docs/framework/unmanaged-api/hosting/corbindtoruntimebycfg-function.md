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
ms.openlocfilehash: bbba208296dd2099c9da58c81ff66fddc78fdc86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093819"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="e9ca1-102">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="e9ca1-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="e9ca1-103">Carica common language runtime (CLR) in un processo usando le informazioni sulla versione che viene letto da un file XML.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="e9ca1-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9ca1-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9ca1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9ca1-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e9ca1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9ca1-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="e9ca1-107">[in] Un puntatore a un `IStream` che legge il file XML.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="e9ca1-108">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-108">[in] Reserved for future use.</span></span> <span data-ttu-id="e9ca1-109">Usare 0 (zero) come valore.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="e9ca1-110">[in] Valore di [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumerazione che specifica il comportamento di avvio di CLR.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e9ca1-111">[in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o il [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e9ca1-112">I valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e9ca1-113">[in] Il `IID` tra il `ICorRuntimeHost` o il `ICLRRuntimeHost` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="e9ca1-114">Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e9ca1-115">[out] Un puntatore all'indirizzo dell'interfaccia restituita.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9ca1-116">Note</span><span class="sxs-lookup"><span data-stu-id="e9ca1-116">Remarks</span></span>  
 <span data-ttu-id="e9ca1-117">Il formato del file XML è modellato il file di configurazione dell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="e9ca1-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="e9ca1-118">Per altre informazioni sui file XML, vedere [Schema di File di configurazione](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="e9ca1-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9ca1-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9ca1-119">Requirements</span></span>  
 <span data-ttu-id="e9ca1-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9ca1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9ca1-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9ca1-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9ca1-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9ca1-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9ca1-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ca1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ca1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9ca1-124">See also</span></span>

- [<span data-ttu-id="e9ca1-125">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="e9ca1-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="e9ca1-126">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="e9ca1-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="e9ca1-127">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="e9ca1-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="e9ca1-128">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e9ca1-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="e9ca1-129">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e9ca1-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="e9ca1-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="e9ca1-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
