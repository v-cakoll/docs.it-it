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
ms.openlocfilehash: 9c37a9af6a1532d03fa04ca151605cef7ab5244e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401768"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="35f4f-102">Funzione CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="35f4f-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="35f4f-103">Libera le risorse allocate per il [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="35f4f-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35f4f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35f4f-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35f4f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35f4f-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="35f4f-106">[in, out] Informazioni relative a chi ha apposto il timestamp da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="35f4f-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="35f4f-107">Vedere il [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="35f4f-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35f4f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="35f4f-108">Return Value</span></span>  
 <span data-ttu-id="35f4f-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="35f4f-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="35f4f-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="35f4f-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f4f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35f4f-111">See Also</span></span>  
 [<span data-ttu-id="35f4f-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="35f4f-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
