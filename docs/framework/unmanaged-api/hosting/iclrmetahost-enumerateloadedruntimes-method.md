---
title: Metodo ICLRMetaHost::EnumerateLoadedRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: f89307ad7ed41f872ad66a99be03663ac1f30f13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140980"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="42002-102">Metodo ICLRMetaHost::EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="42002-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="42002-103">Restituisce un'enumerazione che include un puntatore all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) valido per ogni versione di Common Language Runtime (CLR) caricata in un determinato processo.</span><span class="sxs-lookup"><span data-stu-id="42002-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="42002-104">Questo metodo sostituisce la funzione [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="42002-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42002-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42002-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42002-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="42002-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="42002-107">in Handle del processo da controllare per i runtime caricati.</span><span class="sxs-lookup"><span data-stu-id="42002-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="42002-108">out Enumerazione <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> delle interfacce [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) corrispondenti a ogni CLR caricato dal processo.</span><span class="sxs-lookup"><span data-stu-id="42002-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42002-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="42002-109">Return Value</span></span>  
 <span data-ttu-id="42002-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="42002-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="42002-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42002-111">HRESULT</span></span>|<span data-ttu-id="42002-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42002-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42002-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="42002-113">S_OK</span></span>|<span data-ttu-id="42002-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="42002-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="42002-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="42002-115">E_POINTER</span></span>|<span data-ttu-id="42002-116">`ppEnumerator` è null.</span><span class="sxs-lookup"><span data-stu-id="42002-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42002-117">Note</span><span class="sxs-lookup"><span data-stu-id="42002-117">Remarks</span></span>  
 <span data-ttu-id="42002-118">Questo metodo elenca tutti i runtime caricati, anche se sono stati caricati con funzioni deprecate, ad esempio [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="42002-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42002-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42002-119">Requirements</span></span>  
 <span data-ttu-id="42002-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42002-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42002-121">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="42002-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="42002-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="42002-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42002-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42002-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42002-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42002-124">See also</span></span>

- [<span data-ttu-id="42002-125">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="42002-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="42002-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="42002-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
