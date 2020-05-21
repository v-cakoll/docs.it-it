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
ms.openlocfilehash: 09c80c3a56d86943ebe00e5222bb5452ab44e150
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762175"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="febce-102">Metodo ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="febce-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="febce-103">Carica una libreria di .NET Framework dalla Common Language Runtime (CLR) rappresentata da un'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="febce-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="febce-104">Questo metodo sostituisce la funzione [LoadLibraryShim](loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="febce-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="febce-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="febce-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="febce-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="febce-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="febce-107">in Nome dell'assembly da caricare.</span><span class="sxs-lookup"><span data-stu-id="febce-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="febce-108">out Handle per l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="febce-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="febce-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="febce-109">Return Value</span></span>  
 <span data-ttu-id="febce-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="febce-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="febce-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="febce-111">HRESULT</span></span>|<span data-ttu-id="febce-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="febce-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="febce-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="febce-113">S_OK</span></span>|<span data-ttu-id="febce-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="febce-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="febce-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="febce-115">E_POINTER</span></span>|<span data-ttu-id="febce-116">`pwzDllName` o `phndModule` è null.</span><span class="sxs-lookup"><span data-stu-id="febce-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="febce-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="febce-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="febce-118">La memoria disponibile non è sufficiente per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="febce-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="febce-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="febce-119">Remarks</span></span>  
 <span data-ttu-id="febce-120">Questo metodo carica solo le DLL incluse nel pacchetto ridistribuibile .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="febce-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="febce-121">Non è in grado di caricare assembly generati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="febce-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="febce-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="febce-122">Requirements</span></span>  
 <span data-ttu-id="febce-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="febce-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="febce-124">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="febce-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="febce-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="febce-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="febce-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="febce-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febce-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="febce-127">See also</span></span>

- [<span data-ttu-id="febce-128">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="febce-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="febce-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="febce-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="febce-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="febce-130">Hosting</span></span>](index.md)
