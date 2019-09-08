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
ms.openlocfilehash: a8ecada29528b065ddad0abc80a850ee0f347f6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786998"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="882b1-102">Funzione CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="882b1-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="882b1-103">Libera le risorse allocate per la struttura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="882b1-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="882b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="882b1-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="882b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="882b1-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="882b1-106">[in, out] Informazioni relative a chi ha apposto il timestamp da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="882b1-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="882b1-107">Vedere la struttura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="882b1-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="882b1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="882b1-108">Return Value</span></span>  
 <span data-ttu-id="882b1-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="882b1-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="882b1-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="882b1-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="882b1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="882b1-111">See also</span></span>

- [<span data-ttu-id="882b1-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="882b1-112">Authenticode</span></span>](index.md)
