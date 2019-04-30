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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941623"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="26ce0-102">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="26ce0-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="26ce0-103">Libera le risorse allocate per la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="26ce0-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26ce0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26ce0-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26ce0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26ce0-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="26ce0-106">[in, out] Informazioni del firmatario da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="26ce0-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="26ce0-107">Vedere le [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="26ce0-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26ce0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26ce0-108">Return Value</span></span>  
 <span data-ttu-id="26ce0-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="26ce0-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="26ce0-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="26ce0-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ce0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26ce0-111">See also</span></span>

- [<span data-ttu-id="26ce0-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="26ce0-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
