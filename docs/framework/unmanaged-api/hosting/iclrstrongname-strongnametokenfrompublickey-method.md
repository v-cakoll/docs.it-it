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
ms.openlocfilehash: 13c1c505d939c1048eebef3d1d6b2abe493d319e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937414"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="628da-102">Metodo ICLRStrongName::StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="628da-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="628da-103">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="628da-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="628da-104">Un token di nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="628da-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="628da-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="628da-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="628da-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="628da-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="628da-107">in Struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="628da-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="628da-108">in Dimensione, in byte, del `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="628da-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="628da-109">out Token del nome sicuro corrispondente alla chiave passata `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="628da-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="628da-110">Il Common Language Runtime alloca la memoria in cui restituire il token.</span><span class="sxs-lookup"><span data-stu-id="628da-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="628da-111">Il chiamante deve liberare questa memoria usando il metodo [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="628da-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="628da-112">out Dimensione, in byte, del token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="628da-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="628da-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="628da-113">Return Value</span></span>  
 <span data-ttu-id="628da-114">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="628da-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="628da-115">Note</span><span class="sxs-lookup"><span data-stu-id="628da-115">Remarks</span></span>  
 <span data-ttu-id="628da-116">Un token di nome sicuro è il formato abbreviato di una chiave pubblica usata per risparmiare spazio durante l'archiviazione delle informazioni chiave nei metadati.</span><span class="sxs-lookup"><span data-stu-id="628da-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="628da-117">In particolare, i token con nome sicuro vengono utilizzati nei riferimenti ad assembly per fare riferimento all'assembly dipendente.</span><span class="sxs-lookup"><span data-stu-id="628da-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="628da-118">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="628da-118">Requirements</span></span>  
 <span data-ttu-id="628da-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="628da-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="628da-120">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="628da-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="628da-121">**Libreria:** Incluso come risorsa in mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="628da-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="628da-122">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="628da-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="628da-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="628da-123">See also</span></span>

- [<span data-ttu-id="628da-124">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="628da-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="628da-125">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="628da-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="628da-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="628da-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
