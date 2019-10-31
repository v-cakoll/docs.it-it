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
ms.openlocfilehash: 4f0806e0273b111e3398fb8f2884231b96cf1116
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099764"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="af57f-102">Funzione CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="af57f-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="af57f-103">Libera le risorse allocate per la struttura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="af57f-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af57f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af57f-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af57f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af57f-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="af57f-106">[in, out] Informazioni relative a chi ha apposto il timestamp da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="af57f-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="af57f-107">Vedere la struttura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="af57f-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af57f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af57f-108">Return Value</span></span>  
 <span data-ttu-id="af57f-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="af57f-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="af57f-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="af57f-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af57f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af57f-111">See also</span></span>

- [<span data-ttu-id="af57f-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="af57f-112">Authenticode</span></span>](index.md)
