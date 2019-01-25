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
ms.openlocfilehash: 312db617f185467eda7a9ffa0e8db919e2e94566
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702639"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="e1dcd-102">Metodo ICLRMetaHost::EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="e1dcd-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="e1dcd-103">Restituisce un'enumerazione che contiene un valore valido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia per ogni versione di common language runtime (CLR) installato in un computer.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1dcd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1dcd-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1dcd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1dcd-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="e1dcd-106">[out] Enumerazione dei [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfacce che corrispondono a ogni versione di CLR installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1dcd-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1dcd-107">Return Value</span></span>  
 <span data-ttu-id="e1dcd-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e1dcd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1dcd-109">HRESULT</span></span>|<span data-ttu-id="e1dcd-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1dcd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1dcd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1dcd-111">S_OK</span></span>|<span data-ttu-id="e1dcd-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="e1dcd-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e1dcd-113">E_POINTER</span></span>|<span data-ttu-id="e1dcd-114">`ppEnumerator` è null.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1dcd-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1dcd-115">Requirements</span></span>  
 <span data-ttu-id="e1dcd-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1dcd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1dcd-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e1dcd-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1dcd-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e1dcd-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1dcd-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1dcd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1dcd-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1dcd-120">See also</span></span>
- [<span data-ttu-id="e1dcd-121">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="e1dcd-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="e1dcd-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="e1dcd-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
