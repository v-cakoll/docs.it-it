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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140613"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="759b3-102">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="759b3-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="759b3-103">Rappresenta, in formato binario, la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="759b3-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="759b3-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="759b3-105">Members</span><span class="sxs-lookup"><span data-stu-id="759b3-105">Members</span></span>  
  
|<span data-ttu-id="759b3-106">Member</span><span class="sxs-lookup"><span data-stu-id="759b3-106">Member</span></span>|<span data-ttu-id="759b3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="759b3-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="759b3-108">Identificatore per l'algoritmo di firma, di tipo `ALG_ID`, come definito in WinCrypt. h, della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="759b3-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="759b3-109">Identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt. h) della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="759b3-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="759b3-110">Lunghezza in byte della chiave.</span><span class="sxs-lookup"><span data-stu-id="759b3-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="759b3-111">Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="759b3-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="759b3-112">Note</span><span class="sxs-lookup"><span data-stu-id="759b3-112">Remarks</span></span>  
 <span data-ttu-id="759b3-113">La struttura `PublicKeyBlob` viene utilizzata da [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)e altre funzioni con nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="759b3-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="759b3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="759b3-114">Requirements</span></span>  
 <span data-ttu-id="759b3-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="759b3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="759b3-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="759b3-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="759b3-117">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="759b3-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="759b3-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="759b3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759b3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="759b3-119">See also</span></span>

- [<span data-ttu-id="759b3-120">Funzione StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="759b3-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="759b3-121">Funzione StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="759b3-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
