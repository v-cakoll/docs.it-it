---
title: Struttura PublicKeyBlob
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 245d9dc6147f4140e823b79c3816b9bc567ad712
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732687"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="09b8a-102">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="09b8a-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="09b8a-103">Rappresenta, in formato binario, la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="09b8a-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09b8a-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="09b8a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="09b8a-105">Members</span></span>  
  
|<span data-ttu-id="09b8a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="09b8a-106">Member</span></span>|<span data-ttu-id="09b8a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09b8a-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="09b8a-108">L'identificatore per l'algoritmo di firma (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="09b8a-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="09b8a-109">L'identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="09b8a-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="09b8a-110">La lunghezza della chiave in byte.</span><span class="sxs-lookup"><span data-stu-id="09b8a-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="09b8a-111">Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="09b8a-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09b8a-112">Note</span><span class="sxs-lookup"><span data-stu-id="09b8a-112">Remarks</span></span>  
 <span data-ttu-id="09b8a-113">Il `PublicKeyBlob` struttura viene utilizzata dai [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)e altre funzioni di nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="09b8a-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09b8a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09b8a-114">Requirements</span></span>  
 <span data-ttu-id="09b8a-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09b8a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09b8a-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="09b8a-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="09b8a-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="09b8a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09b8a-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09b8a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b8a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09b8a-119">See also</span></span>
- [<span data-ttu-id="09b8a-120">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="09b8a-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="09b8a-121">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="09b8a-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
- [<span data-ttu-id="09b8a-122">Strutture di denominazione sicura</span><span class="sxs-lookup"><span data-stu-id="09b8a-122">Strong Naming Structures</span></span>](https://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
