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
ms.openlocfilehash: 7dbcbf1b66793a67c815b420e6d5fe221febe719
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716882"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="629b4-102">Metodo ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="629b4-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="629b4-103">Carica una raccolta di .NET Framework da common language runtime (CLR) rappresentato da un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="629b4-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="629b4-104">Questo metodo sostituisce le [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="629b4-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="629b4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="629b4-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="629b4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="629b4-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="629b4-107">[in] Il nome dell'assembly da caricare.</span><span class="sxs-lookup"><span data-stu-id="629b4-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="629b4-108">[out] Handle per l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="629b4-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="629b4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="629b4-109">Return Value</span></span>  
 <span data-ttu-id="629b4-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="629b4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="629b4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="629b4-111">HRESULT</span></span>|<span data-ttu-id="629b4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="629b4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="629b4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="629b4-113">S_OK</span></span>|<span data-ttu-id="629b4-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="629b4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="629b4-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="629b4-115">E_POINTER</span></span>|<span data-ttu-id="629b4-116">`pwzDllName` o `phndModule` è null.</span><span class="sxs-lookup"><span data-stu-id="629b4-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="629b4-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="629b4-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="629b4-118">Memoria insufficiente è disponibile per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="629b4-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="629b4-119">Note</span><span class="sxs-lookup"><span data-stu-id="629b4-119">Remarks</span></span>  
 <span data-ttu-id="629b4-120">Questo metodo carica solo le DLL incluse nel pacchetto ridistribuibile di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="629b4-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="629b4-121">Non può caricare gli assembly generati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="629b4-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="629b4-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="629b4-122">Requirements</span></span>  
 <span data-ttu-id="629b4-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="629b4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="629b4-124">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="629b4-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="629b4-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="629b4-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="629b4-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="629b4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629b4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="629b4-127">See also</span></span>
- [<span data-ttu-id="629b4-128">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="629b4-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="629b4-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="629b4-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="629b4-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="629b4-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
