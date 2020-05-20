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
ms.openlocfilehash: 2e22b8a2d0213b3bd766d80218d6f396721a90e1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703762"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="b1301-102">Metodo ICLRMetaHost::EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="b1301-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="b1301-103">Restituisce un'enumerazione che include un puntatore all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) valido per ogni versione di Common Language Runtime (CLR) caricata in un determinato processo.</span><span class="sxs-lookup"><span data-stu-id="b1301-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="b1301-104">Questo metodo sostituisce la funzione [GetVersionFromProcess](getversionfromprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b1301-104">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1301-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1301-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1301-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1301-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="b1301-107">in Handle del processo da controllare per i runtime caricati.</span><span class="sxs-lookup"><span data-stu-id="b1301-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="b1301-108">out <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>Enumerazione delle interfacce [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrispondono a ogni CLR caricato dal processo.</span><span class="sxs-lookup"><span data-stu-id="b1301-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1301-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b1301-109">Return Value</span></span>  
 <span data-ttu-id="b1301-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="b1301-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b1301-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1301-111">HRESULT</span></span>|<span data-ttu-id="b1301-112">Description</span><span class="sxs-lookup"><span data-stu-id="b1301-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1301-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1301-113">S_OK</span></span>|<span data-ttu-id="b1301-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b1301-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b1301-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b1301-115">E_POINTER</span></span>|<span data-ttu-id="b1301-116">`ppEnumerator` è null.</span><span class="sxs-lookup"><span data-stu-id="b1301-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1301-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b1301-117">Remarks</span></span>  
 <span data-ttu-id="b1301-118">Questo metodo elenca tutti i runtime caricati, anche se sono stati caricati con funzioni deprecate, ad esempio [CorBindToRuntime](corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="b1301-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1301-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1301-119">Requirements</span></span>  
 <span data-ttu-id="b1301-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1301-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1301-121">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="b1301-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b1301-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b1301-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1301-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1301-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1301-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1301-124">See also</span></span>

- [<span data-ttu-id="b1301-125">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="b1301-125">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="b1301-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="b1301-126">Hosting</span></span>](index.md)
