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
ms.openlocfilehash: 3fe1f93c621fd567471b9a49e4aa75cb90e6e0e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161161"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="31541-102">Metodo ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="31541-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="31541-103">Carica una raccolta di .NET Framework da common language runtime (CLR) rappresentato da un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="31541-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="31541-104">Questo metodo sostituisce le [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="31541-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31541-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31541-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31541-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="31541-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="31541-107">[in] Il nome dell'assembly da caricare.</span><span class="sxs-lookup"><span data-stu-id="31541-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="31541-108">[out] Handle per l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="31541-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31541-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="31541-109">Return Value</span></span>  
 <span data-ttu-id="31541-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="31541-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="31541-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31541-111">HRESULT</span></span>|<span data-ttu-id="31541-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31541-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31541-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="31541-113">S_OK</span></span>|<span data-ttu-id="31541-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="31541-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="31541-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="31541-115">E_POINTER</span></span>|`pwzDllName` <span data-ttu-id="31541-116">o `phndModule` è null.</span><span class="sxs-lookup"><span data-stu-id="31541-116">or `phndModule` is null.</span></span>|  
|<span data-ttu-id="31541-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="31541-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="31541-118">Memoria insufficiente è disponibile per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="31541-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31541-119">Note</span><span class="sxs-lookup"><span data-stu-id="31541-119">Remarks</span></span>  
 <span data-ttu-id="31541-120">Questo metodo carica solo le DLL incluse nel pacchetto ridistribuibile di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="31541-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="31541-121">Non può caricare gli assembly generati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="31541-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31541-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31541-122">Requirements</span></span>  
 <span data-ttu-id="31541-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31541-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31541-124">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="31541-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="31541-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="31541-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="31541-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="31541-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31541-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31541-127">See also</span></span>

- [<span data-ttu-id="31541-128">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="31541-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="31541-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="31541-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="31541-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="31541-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
