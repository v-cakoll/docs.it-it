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
ms.openlocfilehash: a233e0b8d17b9ee61b1991086f794c9fb20f89e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099818"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="b54c0-102">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="b54c0-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="b54c0-103">Libera le risorse allocate per la struttura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b54c0-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b54c0-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b54c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b54c0-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="b54c0-106">[in, out] Informazioni del firmatario da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="b54c0-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="b54c0-107">Vedere la struttura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b54c0-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b54c0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b54c0-108">Return Value</span></span>  
 <span data-ttu-id="b54c0-109">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b54c0-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b54c0-110">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b54c0-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54c0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b54c0-111">See also</span></span>

- [<span data-ttu-id="b54c0-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b54c0-112">Authenticode</span></span>](index.md)
