---
title: Metodo ICLRStrongName::StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176318"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="6f394-102">Metodo ICLRStrongName::StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="6f394-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="6f394-103">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6f394-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="6f394-104">Un token con nome sicuro è la forma abbreviata di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6f394-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f394-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f394-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f394-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f394-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="6f394-107">[in] Struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="6f394-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="6f394-108">[in] Dimensione, in byte, `pbPublicKeyBlob`di .</span><span class="sxs-lookup"><span data-stu-id="6f394-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="6f394-109">[fuori] Token con nome sicuro corrispondente `pbPublicKeyBlob`alla chiave passata in .</span><span class="sxs-lookup"><span data-stu-id="6f394-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="6f394-110">Common Language Runtime alloca la memoria in cui restituire il token.</span><span class="sxs-lookup"><span data-stu-id="6f394-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="6f394-111">Il chiamante deve liberare questa memoria utilizzando il metodo [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6f394-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="6f394-112">[fuori] Dimensione, in byte, del token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="6f394-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f394-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6f394-113">Return Value</span></span>  
 <span data-ttu-id="6f394-114">`S_OK`se il metodo è stato completato correttamente; in caso contrario, un valore HRESULT che indica un errore (vedere [Valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="6f394-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f394-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6f394-115">Remarks</span></span>  
 <span data-ttu-id="6f394-116">Un token con nome sicuro è la forma abbreviata di una chiave pubblica utilizzata per risparmiare spazio durante l'archiviazione delle informazioni sulla chiave nei metadati.</span><span class="sxs-lookup"><span data-stu-id="6f394-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="6f394-117">In particolare, i token con nome sicuro vengono utilizzati nei riferimenti all'assembly per fare riferimento all'assembly dipendente.</span><span class="sxs-lookup"><span data-stu-id="6f394-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f394-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f394-118">Requirements</span></span>  
 <span data-ttu-id="6f394-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f394-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f394-120">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6f394-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6f394-121">**Biblioteca:** Incluso come risorsa in mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6f394-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="6f394-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f394-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f394-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f394-123">See also</span></span>

- [<span data-ttu-id="6f394-124">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="6f394-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="6f394-125">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="6f394-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="6f394-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6f394-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
