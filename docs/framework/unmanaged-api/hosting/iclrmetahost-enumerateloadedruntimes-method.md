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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b77a01a6adf40c21e0d56853b860982e39b9b27e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779804"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="91c44-102">Metodo ICLRMetaHost::EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="91c44-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="91c44-103">Restituisce un'enumerazione che include un valore valido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntatore a interfaccia per ogni versione di common language runtime (CLR) che viene caricato in un determinato processo.</span><span class="sxs-lookup"><span data-stu-id="91c44-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="91c44-104">Questo metodo sostituisce le [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="91c44-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c44-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91c44-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91c44-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="91c44-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="91c44-107">[in] L'handle del processo per esaminare i runtime caricati.</span><span class="sxs-lookup"><span data-stu-id="91c44-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="91c44-108">[out] Un' <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumerazione degli [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfacce che corrispondono a ogni CLR caricata dal processo.</span><span class="sxs-lookup"><span data-stu-id="91c44-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91c44-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="91c44-109">Return Value</span></span>  
 <span data-ttu-id="91c44-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="91c44-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="91c44-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91c44-111">HRESULT</span></span>|<span data-ttu-id="91c44-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91c44-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91c44-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="91c44-113">S_OK</span></span>|<span data-ttu-id="91c44-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="91c44-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="91c44-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="91c44-115">E_POINTER</span></span>|<span data-ttu-id="91c44-116">`ppEnumerator` è null.</span><span class="sxs-lookup"><span data-stu-id="91c44-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91c44-117">Note</span><span class="sxs-lookup"><span data-stu-id="91c44-117">Remarks</span></span>  
 <span data-ttu-id="91c44-118">Questo metodo è Elenca tutti i runtime caricati, anche se essi sono stati caricati, ad esempio con le funzioni deprecate [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="91c44-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91c44-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91c44-119">Requirements</span></span>  
 <span data-ttu-id="91c44-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91c44-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91c44-121">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="91c44-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="91c44-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="91c44-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91c44-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91c44-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c44-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91c44-124">See also</span></span>

- [<span data-ttu-id="91c44-125">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="91c44-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="91c44-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="91c44-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
