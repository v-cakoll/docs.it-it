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
ms.openlocfilehash: bdb764417b757cd7388c49d7e5cac9a960074820
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142402"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="131b1-102">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="131b1-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="131b1-103">Libera le risorse allocate per la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="131b1-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="131b1-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="131b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="131b1-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="131b1-106">[in, out] Informazioni del firmatario da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="131b1-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="131b1-107">Vedere le [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="131b1-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="131b1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="131b1-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="131b1-109">Se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="131b1-109">if the function succeeds.</span></span> <span data-ttu-id="131b1-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="131b1-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131b1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="131b1-111">See also</span></span>

- [<span data-ttu-id="131b1-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="131b1-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
