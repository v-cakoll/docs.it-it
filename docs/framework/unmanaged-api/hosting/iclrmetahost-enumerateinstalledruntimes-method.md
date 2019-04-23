---
title: Metodo ICLRMetaHost::EnumerateInstalledRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09931dce7afdb7944cf9912b5146e44fda131935
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173407"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="4212a-102">Metodo ICLRMetaHost::EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="4212a-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="4212a-103">Restituisce un'enumerazione che contiene un valore valido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia per ogni versione di common language runtime (CLR) installato in un computer.</span><span class="sxs-lookup"><span data-stu-id="4212a-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4212a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4212a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4212a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4212a-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="4212a-106">[out] Enumerazione dei [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfacce che corrispondono a ogni versione di CLR installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="4212a-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4212a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4212a-107">Return Value</span></span>  
 <span data-ttu-id="4212a-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4212a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4212a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4212a-109">HRESULT</span></span>|<span data-ttu-id="4212a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4212a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4212a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4212a-111">S_OK</span></span>|<span data-ttu-id="4212a-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4212a-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="4212a-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4212a-113">E_POINTER</span></span>|<span data-ttu-id="4212a-114">`ppEnumerator` è null.</span><span class="sxs-lookup"><span data-stu-id="4212a-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4212a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4212a-115">Requirements</span></span>  
 <span data-ttu-id="4212a-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4212a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4212a-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4212a-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4212a-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4212a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4212a-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4212a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4212a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4212a-120">See also</span></span>

- [<span data-ttu-id="4212a-121">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="4212a-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="4212a-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="4212a-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
