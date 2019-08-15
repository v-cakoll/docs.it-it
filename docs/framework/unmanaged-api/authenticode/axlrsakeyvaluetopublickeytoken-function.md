---
title: _AxlRSAKeyValueToPublicKeyToken (funzione)
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
ms.openlocfilehash: eca6c5fc61d4f7e80046102a560d228fc01e5292
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038420"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="07ca2-102">\_AxlRSAKeyValueToPublicKeyToken (funzione)</span><span class="sxs-lookup"><span data-stu-id="07ca2-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="07ca2-103">Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="07ca2-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ca2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07ca2-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07ca2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="07ca2-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="07ca2-106">in Il BLOB del modulo con codifica Base64 (dall' \<elemento modulo >).</span><span class="sxs-lookup"><span data-stu-id="07ca2-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="07ca2-107">Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="07ca2-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="07ca2-108">in BLOB dell'esponente con codifica Base64 (dall'elemento \<> dell'esponente).</span><span class="sxs-lookup"><span data-stu-id="07ca2-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="07ca2-109">Vedere la struttura [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="07ca2-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="07ca2-110">[out] Puntatore a WCHAR \* per ricevere il token di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="07ca2-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07ca2-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="07ca2-111">Return Value</span></span>  
 <span data-ttu-id="07ca2-112">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="07ca2-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="07ca2-113">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="07ca2-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ca2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07ca2-114">See also</span></span>

- [<span data-ttu-id="07ca2-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="07ca2-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
