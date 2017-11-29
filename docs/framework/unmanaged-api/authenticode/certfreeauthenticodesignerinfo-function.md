---
title: Funzione CertFreeAuthenticodeSignerInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeSignerInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f922cdba8bcfce6c9ff4543f6aea5bacfdc60ab0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="fc454-102">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="fc454-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="fc454-103">Libera le risorse allocate per il [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="fc454-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc454-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc454-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc454-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc454-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="fc454-106">[in, out] Informazioni del firmatario da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="fc454-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="fc454-107">Vedere il [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="fc454-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc454-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fc454-108">Return Value</span></span>  
 <span data-ttu-id="fc454-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fc454-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="fc454-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fc454-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc454-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc454-111">See Also</span></span>  
 [<span data-ttu-id="fc454-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="fc454-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
