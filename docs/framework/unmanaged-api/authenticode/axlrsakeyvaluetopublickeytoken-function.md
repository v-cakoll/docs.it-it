---
title: Funzione _AxlRSAKeyValueToPublicKeyToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlRSAKeyValueToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4af27a2abf1a0bcf4d79eda389c5f79f0ecb1eef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="9fcdf-102">Funzione _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="9fcdf-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="9fcdf-103">Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9fcdf-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fcdf-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fcdf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9fcdf-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="9fcdf-106">[in] Il blob dell'elemento Modulus con codifica base64 (dal \<Modulus > elemento).</span><span class="sxs-lookup"><span data-stu-id="9fcdf-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="9fcdf-107">Vedere il [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="9fcdf-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="9fcdf-108">[in] Il blob Exponent con codifica base64 (dal \<esponente > elemento).</span><span class="sxs-lookup"><span data-stu-id="9fcdf-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="9fcdf-109">Vedere il [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="9fcdf-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="9fcdf-110">[out] Puntatore a WCHAR * per ricevere il token di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="9fcdf-110">[out] A pointer to WCHAR * to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fcdf-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9fcdf-111">Return Value</span></span>  
 <span data-ttu-id="9fcdf-112">`S_OK` se la funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9fcdf-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="9fcdf-113">In caso contrario, verrà restituito un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9fcdf-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcdf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fcdf-114">See Also</span></span>  
 [<span data-ttu-id="9fcdf-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="9fcdf-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
