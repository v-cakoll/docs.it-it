---
title: Funzione CertFreeAuthenticodeSignerInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbed2ece8b10c6385341c0af44a81dfa16b6f60c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497483"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="9d409-102">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="9d409-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="9d409-103">Libera le risorse allocate per la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="9d409-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d409-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d409-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d409-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d409-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="9d409-106">[in, out] Informazioni del firmatario da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="9d409-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="9d409-107">Vedere le [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="9d409-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d409-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9d409-108">Return Value</span></span>  
 <span data-ttu-id="9d409-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d409-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="9d409-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9d409-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d409-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d409-111">See also</span></span>
- [<span data-ttu-id="9d409-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="9d409-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
