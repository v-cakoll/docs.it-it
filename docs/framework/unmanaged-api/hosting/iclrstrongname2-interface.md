---
title: Interfaccia ICLRStrongName2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: 9715369f4cf1b2a7078be14a2fc597f735ab6fd3
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763163"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="2ab3f-102">Interfaccia ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="2ab3f-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="2ab3f-103">Offre la possibilità di creare nomi sicuri usando il gruppo SHA-2 di algoritmi hash sicuri (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="2ab3f-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ab3f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2ab3f-104">Methods</span></span>  
  
|<span data-ttu-id="2ab3f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2ab3f-105">Method</span></span>|<span data-ttu-id="2ab3f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ab3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ab3f-107">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="2ab3f-107">StrongNameGetPublicKeyEx Method</span></span>](strongnamegetpublickeyex-method.md)|<span data-ttu-id="2ab3f-108">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="2ab3f-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="2ab3f-109">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="2ab3f-109">StrongNameSignatureVerificationEx2 Method</span></span>](strongnamesignatureverificationex2-method.md)|<span data-ttu-id="2ab3f-110">Verifica la firma di un assembly con nome sicuro e fornisce un mapping dalla chiave ECMA a una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="2ab3f-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ab3f-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2ab3f-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab3f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ab3f-112">Requirements</span></span>  
 <span data-ttu-id="2ab3f-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab3f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab3f-114">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="2ab3f-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2ab3f-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ab3f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ab3f-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab3f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
