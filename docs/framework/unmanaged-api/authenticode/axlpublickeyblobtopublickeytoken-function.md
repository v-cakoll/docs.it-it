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
ms.openlocfilehash: 33b8f47813a3bf43bd69741c9febb150fa3a92e3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099901"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="c9cf4-102">\_funzione AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="c9cf4-102">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="c9cf4-103">Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="c9cf4-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9cf4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9cf4-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9cf4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9cf4-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="c9cf4-106">[in] BLOB a chiave pubblica CSP.</span><span class="sxs-lookup"><span data-stu-id="c9cf4-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="c9cf4-107">[out] Puntatore a WCHAR \* per ricevere l'hash di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="c9cf4-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9cf4-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c9cf4-108">Return Value</span></span>  
 <span data-ttu-id="c9cf4-109">`S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="c9cf4-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9cf4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9cf4-110">See also</span></span>

- [<span data-ttu-id="c9cf4-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="c9cf4-111">Authenticode</span></span>](index.md)
