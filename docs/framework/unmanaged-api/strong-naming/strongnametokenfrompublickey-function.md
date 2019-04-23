---
title: Funzione StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbfd3ae32f4d3033894fdaf6b1bcc880c324e928
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219798"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="b0331-102">Funzione StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="b0331-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="b0331-103">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="b0331-103">Gets a token representing a public key.</span></span> <span data-ttu-id="b0331-104">Un token con nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="b0331-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="b0331-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="b0331-105">This function has been deprecated.</span></span> <span data-ttu-id="b0331-106">Usare la [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="b0331-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0331-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0331-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0331-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0331-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="b0331-109">[in] Una struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi usata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b0331-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="b0331-110">[in] Le dimensioni, in byte, di `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="b0331-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="b0331-111">[out] Il token di nome sicuro corrispondente alla chiave passato `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="b0331-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="b0331-112">Common language runtime alloca la memoria in cui restituire il token.</span><span class="sxs-lookup"><span data-stu-id="b0331-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="b0331-113">Il chiamante deve liberare la memoria usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="b0331-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="b0331-114">[out] Le dimensioni, in byte, del token restituito nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b0331-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0331-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b0331-115">Return Value</span></span>  
 <span data-ttu-id="b0331-116">`true` al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b0331-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0331-117">Note</span><span class="sxs-lookup"><span data-stu-id="b0331-117">Remarks</span></span>  
 <span data-ttu-id="b0331-118">Un token con nome sicuro è il formato abbreviato di una chiave pubblica usata per risparmiare spazio quando si archiviano le informazioni sulla chiave nei metadati.</span><span class="sxs-lookup"><span data-stu-id="b0331-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="b0331-119">In particolare, i token di nome sicuro vengono usati nei riferimenti ad assembly per fare riferimento all'assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="b0331-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="b0331-120">Se il `StrongNameTokenFromPublicKey` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="b0331-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0331-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0331-121">Requirements</span></span>  
 <span data-ttu-id="b0331-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0331-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0331-123">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b0331-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b0331-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b0331-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="b0331-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0331-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0331-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0331-126">See also</span></span>

- [<span data-ttu-id="b0331-127">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="b0331-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="b0331-128">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="b0331-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="b0331-129">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="b0331-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
