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
ms.openlocfilehash: e61a652072b424d1245518c832f9b0856e0f2021
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762604"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="106c8-102">Metodo ICLRStrongName::StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="106c8-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="106c8-103">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="106c8-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="106c8-104">Un token di nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="106c8-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="106c8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="106c8-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="106c8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="106c8-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="106c8-107">in Struttura di tipo [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="106c8-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="106c8-108">in Dimensione, in byte, di `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="106c8-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="106c8-109">out Token del nome sicuro corrispondente alla chiave passata `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="106c8-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="106c8-110">Il Common Language Runtime alloca la memoria in cui restituire il token.</span><span class="sxs-lookup"><span data-stu-id="106c8-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="106c8-111">Il chiamante deve liberare questa memoria usando il metodo [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="106c8-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="106c8-112">out Dimensione, in byte, del token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="106c8-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="106c8-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="106c8-113">Return Value</span></span>  
 <span data-ttu-id="106c8-114">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="106c8-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="106c8-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="106c8-115">Remarks</span></span>  
 <span data-ttu-id="106c8-116">Un token di nome sicuro è il formato abbreviato di una chiave pubblica usata per risparmiare spazio durante l'archiviazione delle informazioni chiave nei metadati.</span><span class="sxs-lookup"><span data-stu-id="106c8-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="106c8-117">In particolare, i token con nome sicuro vengono utilizzati nei riferimenti ad assembly per fare riferimento all'assembly dipendente.</span><span class="sxs-lookup"><span data-stu-id="106c8-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="106c8-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="106c8-118">Requirements</span></span>  
 <span data-ttu-id="106c8-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="106c8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="106c8-120">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="106c8-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="106c8-121">**Libreria:** Incluso come risorsa in mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="106c8-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="106c8-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="106c8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106c8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="106c8-123">See also</span></span>

- [<span data-ttu-id="106c8-124">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="106c8-124">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="106c8-125">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="106c8-125">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="106c8-126">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="106c8-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
