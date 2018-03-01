---
title: Funzione CorBindToCurrentRuntime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0fed8829f8f14833724d1770273ff905d6f5eabf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="e15e9-102">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="e15e9-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="e15e9-103">Carica common language runtime (CLR) in un processo con informazioni sulla versione memorizzate in un file XML.</span><span class="sxs-lookup"><span data-stu-id="e15e9-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="e15e9-104">Il formato del file XML viene modellato in file di configurazione dell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="e15e9-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="e15e9-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="e15e9-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="e15e9-106">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e15e9-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="e15e9-107">Vedere [durante il caricamento di Common Language Runtime in un processo](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span><span class="sxs-lookup"><span data-stu-id="e15e9-107">See [Loading the Common Language Runtime into a Process](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e15e9-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e15e9-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e15e9-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="e15e9-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="e15e9-110">[in] Il nome di un file di configurazione che specifica la versione di Common Language Runtime da caricare.</span><span class="sxs-lookup"><span data-stu-id="e15e9-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="e15e9-111">Se il nome del file non è completa, si presuppone essere nella stessa directory dell'eseguibile che effettua la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e15e9-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="e15e9-112">La versione del runtime da caricare viene descritta dall'attributo di versione nel [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) elemento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e15e9-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="e15e9-113">Se viene specificata alcuna versione, o se il `<requiredRuntime>` elemento non viene trovato, verrà caricata la versione più recente di CLR installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="e15e9-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e15e9-114">[in] Il `CLSID` della coclasse che implementa il [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e15e9-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e15e9-115">Valori supportati sono CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e15e9-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e15e9-116">[in] Il `IID` dell'interfaccia richiesta.</span><span class="sxs-lookup"><span data-stu-id="e15e9-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="e15e9-117">Valori supportati sono IID_ICorRuntimeHost o IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="e15e9-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e15e9-118">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="e15e9-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e15e9-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e15e9-119">Requirements</span></span>  
 <span data-ttu-id="e15e9-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e15e9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e15e9-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e15e9-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e15e9-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e15e9-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e15e9-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e15e9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e15e9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e15e9-124">See Also</span></span>  
 [<span data-ttu-id="e15e9-125">Funzione CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="e15e9-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="e15e9-126">Funzione CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="e15e9-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="e15e9-127">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="e15e9-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="e15e9-128">Funzione CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e15e9-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="e15e9-129">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e15e9-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="e15e9-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="e15e9-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
