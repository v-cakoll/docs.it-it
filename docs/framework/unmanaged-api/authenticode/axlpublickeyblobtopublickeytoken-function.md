---
title: Funzione _AxlPublicKeyBlobToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b2535441da173ee13653c68f25039fd1431261a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147433"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="76f11-102">Funzione _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="76f11-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="76f11-103">Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="76f11-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f11-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76f11-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f11-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76f11-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="76f11-106">[in] BLOB a chiave pubblica CSP.</span><span class="sxs-lookup"><span data-stu-id="76f11-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="76f11-107">[out] Puntatore a WCHAR \* per ricevere l'hash di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="76f11-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76f11-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="76f11-108">Return Value</span></span>  
 <span data-ttu-id="76f11-109">`S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="76f11-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f11-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76f11-110">See also</span></span>

- [<span data-ttu-id="76f11-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="76f11-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
