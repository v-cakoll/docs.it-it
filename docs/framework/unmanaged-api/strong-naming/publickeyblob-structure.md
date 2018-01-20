---
title: Struttura PublicKeyBlob
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1f04c692b7549c4d7d8d431591eeb867b673d9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="80831-102">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="80831-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="80831-103">Rappresenta la chiave pubblica di una coppia di chiavi pubblica/privata, in formato binario.</span><span class="sxs-lookup"><span data-stu-id="80831-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80831-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80831-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="80831-105">Membri</span><span class="sxs-lookup"><span data-stu-id="80831-105">Members</span></span>  
  
|<span data-ttu-id="80831-106">Membro</span><span class="sxs-lookup"><span data-stu-id="80831-106">Member</span></span>|<span data-ttu-id="80831-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80831-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="80831-108">L'identificatore per l'algoritmo di firma (di tipo `ALG_ID`, come definito in WinCrypt) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="80831-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="80831-109">L'identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="80831-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="80831-110">La lunghezza della chiave in byte.</span><span class="sxs-lookup"><span data-stu-id="80831-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="80831-111">Una matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="80831-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80831-112">Note</span><span class="sxs-lookup"><span data-stu-id="80831-112">Remarks</span></span>  
 <span data-ttu-id="80831-113">Il `PublicKeyBlob` struttura viene utilizzata dalla [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)e altre funzioni di nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="80831-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80831-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80831-114">Requirements</span></span>  
 <span data-ttu-id="80831-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80831-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80831-116">**Intestazione:** StrongName. H</span><span class="sxs-lookup"><span data-stu-id="80831-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="80831-117">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80831-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80831-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80831-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80831-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80831-119">See Also</span></span>  
 [<span data-ttu-id="80831-120">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="80831-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="80831-121">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="80831-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="80831-122">Strutture di denominazione sicura</span><span class="sxs-lookup"><span data-stu-id="80831-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
