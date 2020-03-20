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
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175057"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="0195a-102">Funzione StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="0195a-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="0195a-103">Ottiene un token che rappresenta una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="0195a-103">Gets a token representing a public key.</span></span> <span data-ttu-id="0195a-104">Un token con nome sicuro è la forma abbreviata di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="0195a-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="0195a-105">Questa funzione è deprecata.</span><span class="sxs-lookup"><span data-stu-id="0195a-105">This function has been deprecated.</span></span> <span data-ttu-id="0195a-106">Utilizzare invece il metodo [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0195a-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0195a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0195a-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0195a-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="0195a-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="0195a-109">[in] Struttura di tipo [PublicKeyBlob](publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0195a-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="0195a-110">[in] Dimensione, in byte, `pbPublicKeyBlob`di .</span><span class="sxs-lookup"><span data-stu-id="0195a-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="0195a-111">[fuori] Token con nome sicuro corrispondente `pbPublicKeyBlob`alla chiave passata in .</span><span class="sxs-lookup"><span data-stu-id="0195a-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="0195a-112">Common Language Runtime alloca la memoria in cui restituire il token.</span><span class="sxs-lookup"><span data-stu-id="0195a-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="0195a-113">Il chiamante deve liberare questa memoria utilizzando la funzione [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)</span><span class="sxs-lookup"><span data-stu-id="0195a-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="0195a-114">[fuori] Dimensione, in byte, del token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="0195a-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0195a-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0195a-115">Return Value</span></span>  
 <span data-ttu-id="0195a-116">`true`al termine del successo; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="0195a-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0195a-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0195a-117">Remarks</span></span>  
 <span data-ttu-id="0195a-118">Un token con nome sicuro è la forma abbreviata di una chiave pubblica utilizzata per risparmiare spazio durante l'archiviazione delle informazioni sulla chiave nei metadati.</span><span class="sxs-lookup"><span data-stu-id="0195a-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="0195a-119">In particolare, i token con nome sicuro vengono utilizzati nei riferimenti all'assembly per fare riferimento all'assembly dipendente.</span><span class="sxs-lookup"><span data-stu-id="0195a-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="0195a-120">Se `StrongNameTokenFromPublicKey` la funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="0195a-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0195a-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0195a-121">Requirements</span></span>  
 <span data-ttu-id="0195a-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0195a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0195a-123">**Intestazione:** NomeForte.h</span><span class="sxs-lookup"><span data-stu-id="0195a-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0195a-124">**Biblioteca:** Incluso come risorsa in mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0195a-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="0195a-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0195a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0195a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0195a-126">See also</span></span>

- [<span data-ttu-id="0195a-127">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="0195a-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="0195a-128">Metodo StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="0195a-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="0195a-129">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="0195a-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
