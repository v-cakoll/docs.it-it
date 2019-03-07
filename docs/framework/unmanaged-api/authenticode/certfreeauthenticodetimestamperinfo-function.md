---
title: Funzione CertFreeAuthenticodeTimestamperInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 082ed24eb65de12f337ab4a379b088da0f6eea5a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497379"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="7d2ed-102">Funzione CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="7d2ed-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="7d2ed-103">Libera le risorse allocate per la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="7d2ed-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d2ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d2ed-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d2ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d2ed-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="7d2ed-106">[in, out] Informazioni relative a chi ha apposto il timestamp da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="7d2ed-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="7d2ed-107">Vedere le [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="7d2ed-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d2ed-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7d2ed-108">Return Value</span></span>  
 <span data-ttu-id="7d2ed-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7d2ed-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="7d2ed-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7d2ed-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2ed-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d2ed-111">See also</span></span>
- [<span data-ttu-id="7d2ed-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="7d2ed-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
