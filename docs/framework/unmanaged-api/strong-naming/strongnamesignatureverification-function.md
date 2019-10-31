---
title: Funzione StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
ms.openlocfilehash: 7dd61be008ba08ca2b28ae3e7e8ff6326f8a41d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129241"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="5fb75-102">Funzione StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="5fb75-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="5fb75-103">Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati.</span><span class="sxs-lookup"><span data-stu-id="5fb75-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="5fb75-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="5fb75-104">This function has been deprecated.</span></span> <span data-ttu-id="5fb75-105">Usare invece il metodo [ICLRStrongName:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5fb75-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb75-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fb75-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fb75-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fb75-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5fb75-108">in Percorso del file eseguibile (con estensione dll o exe) portatile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="5fb75-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="5fb75-109">in Flag per modificare il comportamento di verifica.</span><span class="sxs-lookup"><span data-stu-id="5fb75-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="5fb75-110">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fb75-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="5fb75-111">`SN_INFLAG_FORCE_VER` (0x00000001): impone la verifica anche se è necessario eseguire l'override delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="5fb75-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="5fb75-112">`SN_INFLAG_INSTALL` (0x00000002): specifica che questa è la prima volta che il manifesto viene verificato.</span><span class="sxs-lookup"><span data-stu-id="5fb75-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="5fb75-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="5fb75-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="5fb75-114">`SN_INFLAG_USER_ACCESS` (0x00000008): specifica che l'assembly sarà accessibile solo all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="5fb75-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="5fb75-115">`SN_INFLAG_ALL_ACCESS` (0x00000010): specifica che la cache non fornirà alcuna garanzia di restrizione di accesso.</span><span class="sxs-lookup"><span data-stu-id="5fb75-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="5fb75-116">`SN_INFLAG_RUNTIME` (0x80000000)-riservato per il debug interno.</span><span class="sxs-lookup"><span data-stu-id="5fb75-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="5fb75-117">out Flag che indicano se la firma del nome sicuro è stata verificata.</span><span class="sxs-lookup"><span data-stu-id="5fb75-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="5fb75-118">È supportato il valore seguente:</span><span class="sxs-lookup"><span data-stu-id="5fb75-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="5fb75-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="5fb75-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fb75-120">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5fb75-120">Return Value</span></span>  
 <span data-ttu-id="5fb75-121">`true` se la verifica ha avuto esito positivo; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5fb75-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fb75-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fb75-122">Requirements</span></span>  
 <span data-ttu-id="5fb75-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fb75-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fb75-124">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5fb75-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5fb75-125">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5fb75-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5fb75-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fb75-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb75-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fb75-127">See also</span></span>

- [<span data-ttu-id="5fb75-128">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="5fb75-128">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="5fb75-129">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="5fb75-129">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="5fb75-130">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5fb75-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
