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
ms.openlocfilehash: 56333165d179abd79e82f1416342a2700029eb12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401674"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="75a87-102">Funzione _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="75a87-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="75a87-103">Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="75a87-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a87-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75a87-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75a87-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75a87-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="75a87-106">[in] BLOB a chiave pubblica CSP.</span><span class="sxs-lookup"><span data-stu-id="75a87-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="75a87-107">[out] Puntatore a WCHAR \* per ricevere l'hash di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="75a87-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75a87-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="75a87-108">Return Value</span></span>  
 <span data-ttu-id="75a87-109">`S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="75a87-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a87-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75a87-110">See Also</span></span>  
 [<span data-ttu-id="75a87-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="75a87-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
