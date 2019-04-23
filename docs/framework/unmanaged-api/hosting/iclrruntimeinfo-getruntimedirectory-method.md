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
ms.openlocfilehash: 5c09f57ad805b4ba17b4bdafd3ced533199277a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196684"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="8422a-102">Metodo ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="8422a-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="8422a-103">Ottiene la directory di installazione di common language runtime (CLR) associato a questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8422a-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="8422a-104">Questo metodo sostituisce le [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) funzione fornita nelle versioni di .NET Framework 2.0, 3.0 e 3.5.</span><span class="sxs-lookup"><span data-stu-id="8422a-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8422a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8422a-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8422a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8422a-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="8422a-107">[out] Restituisce la directory di installazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="8422a-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="8422a-108">Il percorso di installazione è completo. ad esempio, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="8422a-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="8422a-109">[in, out] Specifica la dimensione del `pwzBuffer` per evitare i sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="8422a-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="8422a-110">Se `pwzBuffer` è null, `pchBuffer` restituisce la dimensione necessaria della `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="8422a-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8422a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8422a-111">Return Value</span></span>  
 <span data-ttu-id="8422a-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="8422a-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8422a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8422a-113">HRESULT</span></span>|<span data-ttu-id="8422a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8422a-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8422a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8422a-115">S_OK</span></span>|<span data-ttu-id="8422a-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="8422a-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="8422a-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8422a-117">E_POINTER</span></span>|<span data-ttu-id="8422a-118">`pwzBuffer` o `pchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="8422a-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8422a-119">Note</span><span class="sxs-lookup"><span data-stu-id="8422a-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8422a-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8422a-120">Requirements</span></span>  
 <span data-ttu-id="8422a-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8422a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8422a-122">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8422a-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8422a-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8422a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8422a-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8422a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8422a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8422a-125">See also</span></span>

- [<span data-ttu-id="8422a-126">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="8422a-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8422a-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="8422a-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
