---
title: Funzione _AxlRSAKeyValueToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ef73f0f7599fdff887437756a5995591fd8ec89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402411"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="f659c-102">Funzione _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="f659c-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="f659c-103">Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="f659c-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f659c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f659c-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f659c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f659c-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="f659c-106">[in] Il blob dell'elemento Modulus con codifica base64 (dal \<Modulus > elemento).</span><span class="sxs-lookup"><span data-stu-id="f659c-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="f659c-107">Vedere il [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="f659c-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="f659c-108">[in] Il blob Exponent con codifica base64 (dal \<esponente > elemento).</span><span class="sxs-lookup"><span data-stu-id="f659c-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="f659c-109">Vedere il [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="f659c-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="f659c-110">[out] Puntatore a WCHAR \* per ricevere il token di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="f659c-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f659c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f659c-111">Return Value</span></span>  
 <span data-ttu-id="f659c-112">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f659c-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="f659c-113">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f659c-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f659c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f659c-114">See Also</span></span>  
 [<span data-ttu-id="f659c-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f659c-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
