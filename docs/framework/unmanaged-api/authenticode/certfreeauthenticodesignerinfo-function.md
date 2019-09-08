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
ms.openlocfilehash: 357a2ca0ffc733adb14a21624cbe28fb754c8240
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776724"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="fe430-102">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="fe430-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="fe430-103">Libera le risorse allocate per la struttura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="fe430-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe430-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe430-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe430-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe430-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="fe430-106">[in, out] Informazioni del firmatario da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="fe430-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="fe430-107">Vedere la struttura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="fe430-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe430-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe430-108">Return Value</span></span>  
 <span data-ttu-id="fe430-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fe430-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="fe430-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fe430-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe430-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe430-111">See also</span></span>

- [<span data-ttu-id="fe430-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="fe430-112">Authenticode</span></span>](index.md)
