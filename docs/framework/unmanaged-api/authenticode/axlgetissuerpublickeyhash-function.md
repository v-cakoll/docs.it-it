---
title: Funzione _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b197aa539e60a9dbcee55cf190c44b45da3a5fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402015"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="b1e4e-102">Funzione _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="b1e4e-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="b1e4e-103">Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.</span><span class="sxs-lookup"><span data-stu-id="b1e4e-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1e4e-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1e4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1e4e-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="b1e4e-106">[in] BLOB a chiave pubblica CSP.</span><span class="sxs-lookup"><span data-stu-id="b1e4e-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="b1e4e-107">Vedere il [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="b1e4e-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="b1e4e-108">[out] Puntatore a WCHAR \* per ricevere il token di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="b1e4e-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1e4e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b1e4e-109">Return Value</span></span>  
 <span data-ttu-id="b1e4e-110">`S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="b1e4e-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e4e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1e4e-111">See Also</span></span>  
 [<span data-ttu-id="b1e4e-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b1e4e-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
