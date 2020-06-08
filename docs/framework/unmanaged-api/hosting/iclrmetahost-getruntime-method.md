---
title: Metodo ICLRMetaHost::GetRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
ms.openlocfilehash: d482e25c7bf0f028e2478c8e7b7863bc54d7aeb9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504193"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="45002-102">Metodo ICLRMetaHost::GetRuntime</span><span class="sxs-lookup"><span data-stu-id="45002-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="45002-103">Ottiene l'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrisponde a una particolare versione di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="45002-103">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="45002-104">Questo metodo sostituisce la funzione [CorBindToRuntimeEx](corbindtoruntimeex-function.md) utilizzata con il flag [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="45002-104">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45002-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45002-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45002-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="45002-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="45002-107">in La versione di compilazione .NET Framework archiviata nei metadati, nel formato "v*a*. *B*[.\* X\*] ".</span><span class="sxs-lookup"><span data-stu-id="45002-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="45002-108">*A*, *B*e *X* sono numeri decimali che corrispondono alla versione principale, alla versione secondaria e al numero di Build.</span><span class="sxs-lookup"><span data-stu-id="45002-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45002-109">Questo parametro deve corrispondere al nome della directory per la versione .NET Framework, come appare in C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="45002-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="45002-110">I valori di esempio sono "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" e "v 4.0. *X*", dove *x* dipende dal numero di build installato.</span><span class="sxs-lookup"><span data-stu-id="45002-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="45002-111">Il prefisso "v" è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="45002-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="45002-112">in Identificatore dell'interfaccia desiderata.</span><span class="sxs-lookup"><span data-stu-id="45002-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="45002-113">Attualmente, l'unico valore valido per questo parametro è IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="45002-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="45002-114">out Puntatore all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrisponde al runtime richiesto.</span><span class="sxs-lookup"><span data-stu-id="45002-114">[out] A pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45002-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45002-115">Return Value</span></span>  
 <span data-ttu-id="45002-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="45002-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="45002-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45002-117">HRESULT</span></span>|<span data-ttu-id="45002-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45002-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45002-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="45002-119">S_OK</span></span>|<span data-ttu-id="45002-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="45002-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="45002-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="45002-121">E_POINTER</span></span>|<span data-ttu-id="45002-122">`pwzVersion` o `ppRuntime` è null.</span><span class="sxs-lookup"><span data-stu-id="45002-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45002-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="45002-123">Remarks</span></span>  
 <span data-ttu-id="45002-124">Questo metodo interagisce costantemente con le interfacce legacy, ad esempio l'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) e le funzioni legacy, ad esempio le funzioni deprecate `CorBindTo*` (vedere [funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md) nell'API di hosting .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="45002-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="45002-125">Ovvero, i runtime caricati con l'API legacy sono visibili alla nuova API e i runtime caricati con la nuova API sono visibili all'API legacy.</span><span class="sxs-lookup"><span data-stu-id="45002-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45002-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45002-126">Requirements</span></span>  
 <span data-ttu-id="45002-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45002-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45002-128">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="45002-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="45002-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="45002-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45002-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45002-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45002-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45002-131">See also</span></span>

- [<span data-ttu-id="45002-132">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="45002-132">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="45002-133">Interfacce di hosting CLR deprecate e coclassi</span><span class="sxs-lookup"><span data-stu-id="45002-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="45002-134">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="45002-134">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="45002-135">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="45002-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="45002-136">Hosting</span><span class="sxs-lookup"><span data-stu-id="45002-136">Hosting</span></span>](index.md)
