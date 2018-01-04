---
title: Metodo ICLRRuntimeInfo::GetDefaultStartupFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b278a791c7e5418322a80bc6478f75791a35af8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="02fde-102">Metodo ICLRRuntimeInfo::GetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="02fde-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="02fde-103">Ottiene i flag di avvio e di un file di configurazione di host che verrà utilizzato per avviare il runtime.</span><span class="sxs-lookup"><span data-stu-id="02fde-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02fde-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02fde-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02fde-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="02fde-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="02fde-106">[out] Un puntatore per i flag di avvio host attualmente impostati.</span><span class="sxs-lookup"><span data-stu-id="02fde-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="02fde-107">[out] Puntatore al percorso di directory del file di configurazione host corrente.</span><span class="sxs-lookup"><span data-stu-id="02fde-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="02fde-108">[in, out] In input, le dimensioni di `pwzHostConfigFile`, per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="02fde-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="02fde-109">Se `pwzHostConfigFile` è null, il metodo restituisce la dimensione necessaria della `pwzHostConfigFile` per pre-allocazione.</span><span class="sxs-lookup"><span data-stu-id="02fde-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02fde-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="02fde-110">Return Value</span></span>  
 <span data-ttu-id="02fde-111">Questo metodo restituisce il valore HRESULT specifico seguente nonché gli errori HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="02fde-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="02fde-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02fde-112">HRESULT</span></span>|<span data-ttu-id="02fde-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02fde-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02fde-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="02fde-114">S_OK</span></span>|<span data-ttu-id="02fde-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="02fde-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02fde-116">Note</span><span class="sxs-lookup"><span data-stu-id="02fde-116">Remarks</span></span>  
 <span data-ttu-id="02fde-117">Questo metodo restituisce i valori di flag predefiniti (`STARTUP_CONCURRENT_GC` e `NULL`), i valori forniti da una chiamata precedente a o il [SetDefaultStartupFlags (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), o i valori impostati da qualsiasi il `CorBind*` metodi se vengono associati a questo runtime.</span><span class="sxs-lookup"><span data-stu-id="02fde-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02fde-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02fde-118">Requirements</span></span>  
 <span data-ttu-id="02fde-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02fde-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02fde-120">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="02fde-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="02fde-121">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02fde-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02fde-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02fde-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fde-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02fde-123">See Also</span></span>  
 [<span data-ttu-id="02fde-124">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="02fde-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="02fde-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="02fde-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="02fde-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="02fde-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
