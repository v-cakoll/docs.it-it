---
title: Metodo ICLRRuntimeInfo::GetProcAddress
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetProcAddress
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b8af06a52a3961bb3e551375350dee849343b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="de106-102">Metodo ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="de106-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="de106-103">Ottiene l'indirizzo di una funzione specificata è stata esportata da common language runtime (CLR) associato a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="de106-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="de106-104">Questo metodo sostituisce il [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="de106-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de106-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de106-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de106-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="de106-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="de106-107">[in] Il nome della funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="de106-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="de106-108">[out] L'indirizzo della funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="de106-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de106-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="de106-109">Return Value</span></span>  
 <span data-ttu-id="de106-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="de106-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="de106-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de106-111">HRESULT</span></span>|<span data-ttu-id="de106-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de106-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de106-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="de106-113">S_OK</span></span>|<span data-ttu-id="de106-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="de106-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="de106-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="de106-115">E_POINTER</span></span>|<span data-ttu-id="de106-116">`pszProcName` o `ppProc` è null.</span><span class="sxs-lookup"><span data-stu-id="de106-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="de106-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="de106-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="de106-118">La funzione specificata non è una funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="de106-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de106-119">Note</span><span class="sxs-lookup"><span data-stu-id="de106-119">Remarks</span></span>  
 <span data-ttu-id="de106-120">Questo metodo, CLR essere caricato, ma non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="de106-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de106-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de106-121">Requirements</span></span>  
 <span data-ttu-id="de106-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de106-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de106-123">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="de106-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="de106-124">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de106-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de106-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de106-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de106-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de106-126">See Also</span></span>  
 [<span data-ttu-id="de106-127">ICLRRuntimeInfo (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="de106-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="de106-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="de106-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="de106-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="de106-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
