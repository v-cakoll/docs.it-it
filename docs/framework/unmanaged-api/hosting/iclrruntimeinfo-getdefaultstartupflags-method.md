---
title: Metodo ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c39ad4638c7db45c481bd3dfccb0a82759397aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072580"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="63536-102">Metodo ICLRRuntimeInfo::GetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="63536-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="63536-103">Ottiene il flag di avvio e i file di configurazione di host che verrà usato per avviare il runtime.</span><span class="sxs-lookup"><span data-stu-id="63536-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63536-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63536-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63536-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63536-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="63536-106">[out] Puntatore ai flag di avvio host attualmente impostati.</span><span class="sxs-lookup"><span data-stu-id="63536-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="63536-107">[out] Un puntatore al percorso di directory del file di configurazione host corrente.</span><span class="sxs-lookup"><span data-stu-id="63536-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="63536-108">[in, out] In input, le dimensioni di `pwzHostConfigFile`, per evitare i sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="63536-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="63536-109">Se `pwzHostConfigFile` è null, il metodo restituisce la dimensione necessaria della `pwzHostConfigFile` per pre-allocazione.</span><span class="sxs-lookup"><span data-stu-id="63536-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63536-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="63536-110">Return Value</span></span>  
 <span data-ttu-id="63536-111">Questo metodo restituisce il valore HRESULT specifico seguente, nonché gli errori HRESULT che indicano un errore di metodo.</span><span class="sxs-lookup"><span data-stu-id="63536-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="63536-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63536-112">HRESULT</span></span>|<span data-ttu-id="63536-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63536-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63536-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="63536-114">S_OK</span></span>|<span data-ttu-id="63536-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="63536-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63536-116">Note</span><span class="sxs-lookup"><span data-stu-id="63536-116">Remarks</span></span>  
 <span data-ttu-id="63536-117">Questo metodo restituisce i valori di flag predefiniti (`STARTUP_CONCURRENT_GC` e `NULL`), o i valori forniti da una precedente chiamata ai [SetDefaultStartupFlags (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), o i valori impostati da uno qualsiasi del `CorBind*` metodi se vengono associati a questa versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="63536-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63536-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63536-118">Requirements</span></span>  
 <span data-ttu-id="63536-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63536-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63536-120">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="63536-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="63536-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="63536-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="63536-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="63536-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63536-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63536-123">See also</span></span>

- [<span data-ttu-id="63536-124">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="63536-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="63536-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="63536-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="63536-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="63536-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
