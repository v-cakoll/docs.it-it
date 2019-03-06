---
title: Metodo ICLRRuntimeInfo::LoadLibrary
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 878d68dd690a8764ef26f5f180fabd6c22841a25
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466836"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="e12ad-102">Metodo ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="e12ad-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="e12ad-103">Carica una raccolta di .NET Framework da common language runtime (CLR) rappresentato da un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e12ad-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="e12ad-104">Questo metodo sostituisce le [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="e12ad-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12ad-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e12ad-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e12ad-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e12ad-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="e12ad-107">[in] Il nome dell'assembly da caricare.</span><span class="sxs-lookup"><span data-stu-id="e12ad-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="e12ad-108">[out] Handle per l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="e12ad-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e12ad-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e12ad-109">Return Value</span></span>  
 <span data-ttu-id="e12ad-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="e12ad-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e12ad-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e12ad-111">HRESULT</span></span>|<span data-ttu-id="e12ad-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e12ad-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e12ad-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e12ad-113">S_OK</span></span>|<span data-ttu-id="e12ad-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e12ad-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e12ad-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e12ad-115">E_POINTER</span></span>|<span data-ttu-id="e12ad-116">`pwzDllName` o `phndModule` è null.</span><span class="sxs-lookup"><span data-stu-id="e12ad-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="e12ad-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e12ad-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e12ad-118">Memoria insufficiente è disponibile per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="e12ad-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e12ad-119">Note</span><span class="sxs-lookup"><span data-stu-id="e12ad-119">Remarks</span></span>  
 <span data-ttu-id="e12ad-120">Questo metodo carica solo le DLL incluse nel pacchetto ridistribuibile di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e12ad-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="e12ad-121">Non può caricare gli assembly generati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e12ad-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e12ad-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e12ad-122">Requirements</span></span>  
 <span data-ttu-id="e12ad-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e12ad-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e12ad-124">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e12ad-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e12ad-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e12ad-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e12ad-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e12ad-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12ad-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e12ad-127">See also</span></span>
- [<span data-ttu-id="e12ad-128">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e12ad-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="e12ad-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="e12ad-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e12ad-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="e12ad-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
