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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176955"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="f9726-102">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="f9726-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="f9726-103">Rappresenta, in formato binario, la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="f9726-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9726-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9726-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="f9726-105">Members</span><span class="sxs-lookup"><span data-stu-id="f9726-105">Members</span></span>  
  
|<span data-ttu-id="f9726-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f9726-106">Member</span></span>|<span data-ttu-id="f9726-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9726-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="f9726-108">Identificatore per l'algoritmo `ALG_ID`di firma (di tipo , come definito in WinCrypt.h) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="f9726-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="f9726-109">Identificatore per l'algoritmo `ALG_ID`hash (di tipo , come definito in WinCrypt.h) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="f9726-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="f9726-110">Lunghezza della chiave in byte.</span><span class="sxs-lookup"><span data-stu-id="f9726-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="f9726-111">Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="f9726-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9726-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f9726-112">Remarks</span></span>  
 <span data-ttu-id="f9726-113">La `PublicKeyBlob` struttura viene utilizzata da [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)e da altre funzioni con nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="f9726-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9726-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9726-114">Requirements</span></span>  
 <span data-ttu-id="f9726-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9726-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9726-116">**Intestazione:** NomeForte.h</span><span class="sxs-lookup"><span data-stu-id="f9726-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f9726-117">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9726-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9726-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9726-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9726-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9726-119">See also</span></span>

- [<span data-ttu-id="f9726-120">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="f9726-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="f9726-121">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="f9726-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
