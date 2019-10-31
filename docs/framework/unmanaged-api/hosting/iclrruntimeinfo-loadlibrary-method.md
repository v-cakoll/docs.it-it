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
ms.openlocfilehash: 8c72f58bb65bd862b0625bfa0398b26bad0197e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192078"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="34af1-102">Metodo ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="34af1-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="34af1-103">Carica una libreria di .NET Framework dalla Common Language Runtime (CLR) rappresentata da un'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="34af1-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="34af1-104">Questo metodo sostituisce la funzione [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="34af1-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34af1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34af1-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34af1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="34af1-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="34af1-107">in Nome dell'assembly da caricare.</span><span class="sxs-lookup"><span data-stu-id="34af1-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="34af1-108">out Handle per l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="34af1-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34af1-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="34af1-109">Return Value</span></span>  
 <span data-ttu-id="34af1-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="34af1-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="34af1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34af1-111">HRESULT</span></span>|<span data-ttu-id="34af1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34af1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34af1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="34af1-113">S_OK</span></span>|<span data-ttu-id="34af1-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="34af1-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="34af1-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="34af1-115">E_POINTER</span></span>|<span data-ttu-id="34af1-116">`pwzDllName` o `phndModule` è null.</span><span class="sxs-lookup"><span data-stu-id="34af1-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="34af1-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="34af1-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="34af1-118">La memoria disponibile non è sufficiente per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="34af1-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34af1-119">Note</span><span class="sxs-lookup"><span data-stu-id="34af1-119">Remarks</span></span>  
 <span data-ttu-id="34af1-120">Questo metodo carica solo le DLL incluse nel pacchetto ridistribuibile .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34af1-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="34af1-121">Non è in grado di caricare assembly generati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="34af1-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34af1-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34af1-122">Requirements</span></span>  
 <span data-ttu-id="34af1-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34af1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34af1-124">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="34af1-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="34af1-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="34af1-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34af1-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34af1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34af1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34af1-127">See also</span></span>

- [<span data-ttu-id="34af1-128">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="34af1-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="34af1-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="34af1-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="34af1-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="34af1-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
