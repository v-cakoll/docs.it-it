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
ms.openlocfilehash: 680d9c959c57620ff38f8e785c670b451e5805b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741227"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="a7c88-102">Funzione CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="a7c88-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="a7c88-103">Libera le risorse allocate per la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="a7c88-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7c88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7c88-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7c88-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7c88-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="a7c88-106">[in, out] Informazioni relative a chi ha apposto il timestamp da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="a7c88-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="a7c88-107">Vedere le [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) struttura.</span><span class="sxs-lookup"><span data-stu-id="a7c88-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7c88-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a7c88-108">Return Value</span></span>  
 <span data-ttu-id="a7c88-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a7c88-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="a7c88-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a7c88-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c88-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7c88-111">See also</span></span>

- [<span data-ttu-id="a7c88-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="a7c88-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
