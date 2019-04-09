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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173407"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="6755b-102">Metodo ICLRMetaHost::EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="6755b-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="6755b-103">Restituisce un'enumerazione che contiene un valore valido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia per ogni versione di common language runtime (CLR) installato in un computer.</span><span class="sxs-lookup"><span data-stu-id="6755b-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6755b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6755b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6755b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6755b-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="6755b-106">[out] Enumerazione dei [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfacce che corrispondono a ogni versione di CLR installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="6755b-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6755b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6755b-107">Return Value</span></span>  
 <span data-ttu-id="6755b-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="6755b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6755b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6755b-109">HRESULT</span></span>|<span data-ttu-id="6755b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6755b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6755b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6755b-111">S_OK</span></span>|<span data-ttu-id="6755b-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="6755b-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="6755b-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6755b-113">E_POINTER</span></span>|`ppEnumerator` <span data-ttu-id="6755b-114">è null.</span><span class="sxs-lookup"><span data-stu-id="6755b-114">is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6755b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6755b-115">Requirements</span></span>  
 <span data-ttu-id="6755b-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6755b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6755b-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6755b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6755b-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6755b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6755b-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6755b-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6755b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6755b-120">See also</span></span>

- [<span data-ttu-id="6755b-121">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="6755b-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="6755b-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="6755b-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
