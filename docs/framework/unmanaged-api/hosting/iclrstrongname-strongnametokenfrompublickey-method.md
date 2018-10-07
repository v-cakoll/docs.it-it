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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98c0dbbbe65d8f8c0b0196c82db1a8fd2b0ee3dd
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841125"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="d1ae7-102">Metodo ICLRStrongName::StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="d1ae7-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="d1ae7-103">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="d1ae7-104">Un token con nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ae7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1ae7-105">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1ae7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d1ae7-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="d1ae7-107">[in] Una struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi usata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="d1ae7-108">[in] Le dimensioni, in byte, di `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="d1ae7-109">[out] Il token di nome sicuro corrispondente alla chiave passato `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="d1ae7-110">Common language runtime alloca la memoria in cui restituire il token.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="d1ae7-111">Il chiamante deve liberare la memoria usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d1ae7-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="d1ae7-112">[out] Le dimensioni, in byte, del token restituito nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1ae7-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d1ae7-113">Return Value</span></span>  
 <span data-ttu-id="d1ae7-114">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="d1ae7-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1ae7-115">Note</span><span class="sxs-lookup"><span data-stu-id="d1ae7-115">Remarks</span></span>  
 <span data-ttu-id="d1ae7-116">Un token con nome sicuro è il formato abbreviato di una chiave pubblica che consente di risparmiare spazio quando si archiviano le informazioni sulla chiave nei metadati.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="d1ae7-117">In particolare, i token di nome sicuro vengono usati nei riferimenti ad assembly per fare riferimento all'assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d1ae7-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1ae7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1ae7-118">Requirements</span></span>  
 <span data-ttu-id="d1ae7-119">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1ae7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ae7-120">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="d1ae7-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d1ae7-121">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d1ae7-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="d1ae7-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1ae7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ae7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1ae7-123">See Also</span></span>  
 [<span data-ttu-id="d1ae7-124">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="d1ae7-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="d1ae7-125">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="d1ae7-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="d1ae7-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d1ae7-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
