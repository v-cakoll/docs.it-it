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
ms.openlocfilehash: 1a361e04b6f8f39ec0083471d8cb47d5a29376c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000350"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="50023-102">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="50023-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="50023-103">Rappresenta, in formato binario, la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="50023-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50023-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50023-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="50023-105">Membri</span><span class="sxs-lookup"><span data-stu-id="50023-105">Members</span></span>  
  
|<span data-ttu-id="50023-106">Member</span><span class="sxs-lookup"><span data-stu-id="50023-106">Member</span></span>|<span data-ttu-id="50023-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50023-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="50023-108">L'identificatore per l'algoritmo di firma (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="50023-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="50023-109">L'identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="50023-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="50023-110">La lunghezza della chiave in byte.</span><span class="sxs-lookup"><span data-stu-id="50023-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="50023-111">Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="50023-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50023-112">Note</span><span class="sxs-lookup"><span data-stu-id="50023-112">Remarks</span></span>  
 <span data-ttu-id="50023-113">Il `PublicKeyBlob` struttura viene utilizzata dai [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)e altre funzioni di nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="50023-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50023-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50023-114">Requirements</span></span>  
 <span data-ttu-id="50023-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50023-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50023-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="50023-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="50023-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="50023-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50023-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50023-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50023-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50023-119">See also</span></span>

- [<span data-ttu-id="50023-120">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="50023-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="50023-121">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="50023-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
