---
title: Funzione StrongNameTokenFromPublicKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: COM
f1_keywords: StrongNameTokenFromPublicKey
helpviewer_keywords: StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfde09f6383646f24077c3bdc0efa4b31bc50ba0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="92f52-102">Funzione StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="92f52-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="92f52-103">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="92f52-103">Gets a token representing a public key.</span></span> <span data-ttu-id="92f52-104">Un token con nome sicuro è la forma abbreviata di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="92f52-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="92f52-105">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="92f52-105">This function has been deprecated.</span></span> <span data-ttu-id="92f52-106">Utilizzare il [:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="92f52-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92f52-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92f52-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92f52-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="92f52-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="92f52-109">[in] Una struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi usata per generare la firma nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="92f52-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="92f52-110">[in] Le dimensioni, in byte, di `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="92f52-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="92f52-111">[out] Il token con nome sicuro corrispondente alla chiave passata `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="92f52-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="92f52-112">Common language runtime alloca la memoria nel quale restituire il token.</span><span class="sxs-lookup"><span data-stu-id="92f52-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="92f52-113">Il chiamante deve liberare la memoria utilizzando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="92f52-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="92f52-114">[out] Le dimensioni in byte, del token restituito con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="92f52-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92f52-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="92f52-115">Return Value</span></span>  
 <span data-ttu-id="92f52-116">`true`al termine dell'esecuzione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="92f52-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92f52-117">Note</span><span class="sxs-lookup"><span data-stu-id="92f52-117">Remarks</span></span>  
 <span data-ttu-id="92f52-118">Un token con nome sicuro è la forma abbreviata di una chiave pubblica utilizzata per risparmiare spazio quando si archiviano le informazioni sulla chiave nei metadati.</span><span class="sxs-lookup"><span data-stu-id="92f52-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="92f52-119">In particolare, vengono utilizzati i token con nome sicuro nei riferimenti ad assembly per fare riferimento all'assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="92f52-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="92f52-120">Se il `StrongNameTokenFromPublicKey` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="92f52-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92f52-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92f52-121">Requirements</span></span>  
 <span data-ttu-id="92f52-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92f52-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92f52-123">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="92f52-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="92f52-124">**Libreria:** inclusa come risorsa in mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="92f52-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="92f52-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92f52-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f52-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92f52-126">See Also</span></span>  
 [<span data-ttu-id="92f52-127">StrongNameTokenFromPublicKey (metodo)</span><span class="sxs-lookup"><span data-stu-id="92f52-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="92f52-128">StrongNameGetPublicKey (metodo)</span><span class="sxs-lookup"><span data-stu-id="92f52-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="92f52-129">PublicKeyBlob (struttura)</span><span class="sxs-lookup"><span data-stu-id="92f52-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
