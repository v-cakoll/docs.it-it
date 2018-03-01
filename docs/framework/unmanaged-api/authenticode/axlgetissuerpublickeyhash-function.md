---
title: Funzione _AxlGetIssuerPublicKeyHash
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fee2b3e0e74ec13009a9b02d226c6a99b0e2f34b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="61fd2-102">Funzione _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="61fd2-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="61fd2-103">Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.</span><span class="sxs-lookup"><span data-stu-id="61fd2-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61fd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61fd2-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61fd2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="61fd2-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="61fd2-106">[in] BLOB a chiave pubblica CSP.</span><span class="sxs-lookup"><span data-stu-id="61fd2-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="61fd2-107">Vedere il [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="61fd2-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="61fd2-108">[out] Puntatore a WCHAR \* per ricevere il token di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="61fd2-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61fd2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="61fd2-109">Return Value</span></span>  
 <span data-ttu-id="61fd2-110">`S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="61fd2-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61fd2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61fd2-111">See Also</span></span>  
 [<span data-ttu-id="61fd2-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="61fd2-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
