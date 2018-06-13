---
title: Metodo ICLRRuntimeInfo::GetRuntimeDirectory
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f366e736c90ffd8cf588af3a6e5f6240426b9980
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434525"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="b5fbc-102">Metodo ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="b5fbc-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="b5fbc-103">Ottiene la directory di installazione di common language runtime (CLR) associata a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="b5fbc-104">Questo metodo sostituisce il [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) funzione fornita nelle versioni di .NET Framework 2.0, 3.0 e 3.5.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5fbc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5fbc-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5fbc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5fbc-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="b5fbc-107">[out] Restituisce la directory di installazione di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="b5fbc-108">Il percorso di installazione è completo. ad esempio, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="b5fbc-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="b5fbc-109">[in, out] Specifica le dimensioni di `pwzBuffer` per evitare sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="b5fbc-110">Se `pwzBuffer` è null, `pchBuffer` restituisce le dimensioni necessarie di `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5fbc-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b5fbc-111">Return Value</span></span>  
 <span data-ttu-id="b5fbc-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b5fbc-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5fbc-113">HRESULT</span></span>|<span data-ttu-id="b5fbc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5fbc-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5fbc-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5fbc-115">S_OK</span></span>|<span data-ttu-id="b5fbc-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="b5fbc-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b5fbc-117">E_POINTER</span></span>|<span data-ttu-id="b5fbc-118">`pwzBuffer` o `pchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5fbc-119">Note</span><span class="sxs-lookup"><span data-stu-id="b5fbc-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5fbc-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5fbc-120">Requirements</span></span>  
 <span data-ttu-id="b5fbc-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5fbc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5fbc-122">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="b5fbc-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b5fbc-123">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b5fbc-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5fbc-124">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5fbc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5fbc-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5fbc-125">See Also</span></span>  
 [<span data-ttu-id="b5fbc-126">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="b5fbc-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="b5fbc-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="b5fbc-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
