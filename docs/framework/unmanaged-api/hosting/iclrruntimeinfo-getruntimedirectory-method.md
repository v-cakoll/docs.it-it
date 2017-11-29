---
title: Metodo ICLRRuntimeInfo::GetRuntimeDirectory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetRuntimeDirectory
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddaca8232f0b262377c7915852da89cecec09993
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="11a1a-102">Metodo ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="11a1a-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="11a1a-103">Ottiene la directory di installazione di common language runtime (CLR) associata a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="11a1a-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="11a1a-104">Questo metodo sostituisce il [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) funzione fornita nelle versioni di .NET Framework 2.0, 3.0 e 3.5.</span><span class="sxs-lookup"><span data-stu-id="11a1a-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a1a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11a1a-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11a1a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="11a1a-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="11a1a-107">[out] Restituisce la directory di installazione di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="11a1a-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="11a1a-108">Il percorso di installazione è completo. ad esempio, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="11a1a-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="11a1a-109">[in, out] Specifica le dimensioni di `pwzBuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="11a1a-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="11a1a-110">Se `pwzBuffer` è null, `pchBuffer` restituisce le dimensioni necessarie di `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="11a1a-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a1a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="11a1a-111">Return Value</span></span>  
 <span data-ttu-id="11a1a-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="11a1a-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="11a1a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11a1a-113">HRESULT</span></span>|<span data-ttu-id="11a1a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11a1a-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11a1a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="11a1a-115">S_OK</span></span>|<span data-ttu-id="11a1a-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="11a1a-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="11a1a-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="11a1a-117">E_POINTER</span></span>|<span data-ttu-id="11a1a-118">`pwzBuffer` o `pchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="11a1a-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11a1a-119">Note</span><span class="sxs-lookup"><span data-stu-id="11a1a-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a1a-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11a1a-120">Requirements</span></span>  
 <span data-ttu-id="11a1a-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a1a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a1a-122">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="11a1a-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="11a1a-123">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11a1a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11a1a-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a1a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a1a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11a1a-125">See Also</span></span>  
 [<span data-ttu-id="11a1a-126">ICLRRuntimeInfo (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="11a1a-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="11a1a-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="11a1a-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
