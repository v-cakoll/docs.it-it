---
title: Metodo ICLRRuntimeInfo::LoadLibrary
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadLibrary
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b688a4f2557c5ab2ef112e13b411e25ad47b8c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="229ff-102">Metodo ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="229ff-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="229ff-103">Carica una libreria .NET Framework da common language runtime (CLR) rappresentato da un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="229ff-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="229ff-104">Questo metodo sostituisce il [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="229ff-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229ff-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="229ff-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="229ff-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="229ff-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="229ff-107">[in] Il nome dell'assembly da caricare.</span><span class="sxs-lookup"><span data-stu-id="229ff-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="229ff-108">[out] Handle per l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="229ff-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="229ff-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="229ff-109">Return Value</span></span>  
 <span data-ttu-id="229ff-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="229ff-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="229ff-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="229ff-111">HRESULT</span></span>|<span data-ttu-id="229ff-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="229ff-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="229ff-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="229ff-113">S_OK</span></span>|<span data-ttu-id="229ff-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="229ff-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="229ff-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="229ff-115">E_POINTER</span></span>|<span data-ttu-id="229ff-116">`pwzDllName` o `phndModule` è null.</span><span class="sxs-lookup"><span data-stu-id="229ff-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="229ff-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="229ff-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="229ff-118">Memoria insufficiente è disponibile per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="229ff-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="229ff-119">Note</span><span class="sxs-lookup"><span data-stu-id="229ff-119">Remarks</span></span>  
 <span data-ttu-id="229ff-120">Questo metodo carica solo le DLL incluse nel pacchetto ridistribuibile di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="229ff-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="229ff-121">Non può caricare gli assembly generati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="229ff-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="229ff-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="229ff-122">Requirements</span></span>  
 <span data-ttu-id="229ff-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="229ff-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="229ff-124">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="229ff-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="229ff-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="229ff-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="229ff-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="229ff-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="229ff-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="229ff-127">See Also</span></span>  
 [<span data-ttu-id="229ff-128">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="229ff-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="229ff-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="229ff-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="229ff-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="229ff-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
