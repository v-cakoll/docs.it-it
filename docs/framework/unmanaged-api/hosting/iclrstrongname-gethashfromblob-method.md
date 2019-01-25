---
title: Metodo ICLRStrongName::GetHashFromBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b85f8ffade19cee8f0703af823d91a6ea7bf50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710224"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="9cc75-102">Metodo ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="9cc75-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="9cc75-103">Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="9cc75-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cc75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9cc75-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cc75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9cc75-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="9cc75-106">[in] Un puntatore all'indirizzo del blocco di memoria per eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="9cc75-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="9cc75-107">[in] La lunghezza, espressa in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="9cc75-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9cc75-108">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="9cc75-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="9cc75-109">Usa lo zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="9cc75-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9cc75-110">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="9cc75-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9cc75-111">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="9cc75-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9cc75-112">[out] Le dimensioni, in byte, del valore restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="9cc75-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cc75-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9cc75-113">Return Value</span></span>  
 <span data-ttu-id="9cc75-114">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="9cc75-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc75-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9cc75-115">Requirements</span></span>  
 <span data-ttu-id="9cc75-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cc75-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc75-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9cc75-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9cc75-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9cc75-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cc75-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc75-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc75-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cc75-120">See also</span></span>
- [<span data-ttu-id="9cc75-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9cc75-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
