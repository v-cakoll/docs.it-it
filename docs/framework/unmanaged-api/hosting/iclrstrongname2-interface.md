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
ms.openlocfilehash: bc871c29f53a9ea4451a0fc1c747939724b0da87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092236"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="3aef2-102">Interfaccia ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="3aef2-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="3aef2-103">Offre la possibilità di creare nomi sicuri usando il gruppo SHA-2 di algoritmi hash sicuri (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="3aef2-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3aef2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3aef2-104">Methods</span></span>  
  
|<span data-ttu-id="3aef2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3aef2-105">Method</span></span>|<span data-ttu-id="3aef2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aef2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3aef2-107">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="3aef2-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="3aef2-108">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="3aef2-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="3aef2-109">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="3aef2-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="3aef2-110">Verifica la firma di un assembly con nome sicuro e fornisce un mapping dalla chiave ECMA a una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="3aef2-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aef2-111">Note</span><span class="sxs-lookup"><span data-stu-id="3aef2-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aef2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3aef2-112">Requirements</span></span>  
 <span data-ttu-id="3aef2-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aef2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aef2-114">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="3aef2-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3aef2-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3aef2-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3aef2-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aef2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
