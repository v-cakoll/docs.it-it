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
ms.openlocfilehash: b42079d138e754996470e07b884d49c1ebb625c3
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901159"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="ba9b9-102">Metodo ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="ba9b9-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="ba9b9-103">Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba9b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba9b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba9b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba9b9-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="ba9b9-106">in Puntatore all'indirizzo del blocco di memoria di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="ba9b9-107">in Lunghezza, in byte, del blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ba9b9-108">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ba9b9-109">Usare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ba9b9-110">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ba9b9-111">in Dimensioni massime richieste di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ba9b9-112">out Dimensione, in byte, dell'oggetto restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ba9b9-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba9b9-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba9b9-113">Return Value</span></span>  
 <span data-ttu-id="ba9b9-114">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="ba9b9-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba9b9-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ba9b9-115">Requirements</span></span>  
 <span data-ttu-id="ba9b9-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba9b9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba9b9-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ba9b9-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ba9b9-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ba9b9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba9b9-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba9b9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba9b9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba9b9-120">See also</span></span>

- [<span data-ttu-id="ba9b9-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ba9b9-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
