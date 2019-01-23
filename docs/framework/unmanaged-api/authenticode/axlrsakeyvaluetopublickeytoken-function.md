---
title: Funzione AxlRSAKeyValueToPublicKeyToken
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
ms.openlocfilehash: 2a340af9ba196dbcd8618afdd83bcf7e56124bf7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529908"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="44051-102">\_Funzione AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="44051-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="44051-103">Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="44051-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44051-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44051-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a><span data-ttu-id="44051-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44051-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="44051-106">[in] Il blob dell'elemento Modulus con codifica base64 (dalla \<Modulus > elemento).</span><span class="sxs-lookup"><span data-stu-id="44051-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="44051-107">Vedere le [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) struttura.</span><span class="sxs-lookup"><span data-stu-id="44051-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="44051-108">[in] Il blob di Exponent con codifica base64 (dalla \<Exponent > elemento).</span><span class="sxs-lookup"><span data-stu-id="44051-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="44051-109">Vedere le [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) struttura.</span><span class="sxs-lookup"><span data-stu-id="44051-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="44051-110">[out] Puntatore a WCHAR \* per ricevere il token di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="44051-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44051-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="44051-111">Return Value</span></span>  
 <span data-ttu-id="44051-112">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="44051-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="44051-113">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="44051-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44051-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44051-114">See also</span></span>
- [<span data-ttu-id="44051-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="44051-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
