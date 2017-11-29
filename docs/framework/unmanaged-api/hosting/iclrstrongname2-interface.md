---
title: Interfaccia ICLRStrongName2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName2
helpviewer_keywords: ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9e9a88f1064c888d60e363be569d06458299143d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="15b6b-102">Interfaccia ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="15b6b-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="15b6b-103">Fornisce la possibilità di creare nomi sicuri tramite il gruppo di SHA-2 degli algoritmi di Hash di protezione (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="15b6b-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15b6b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="15b6b-104">Methods</span></span>  
  
|<span data-ttu-id="15b6b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="15b6b-105">Method</span></span>|<span data-ttu-id="15b6b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15b6b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15b6b-107">StrongNameGetPublicKeyEx (metodo)</span><span class="sxs-lookup"><span data-stu-id="15b6b-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="15b6b-108">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="15b6b-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="15b6b-109">StrongNameSignatureVerificationEx2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="15b6b-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="15b6b-110">Verifica la firma di un assembly con nome sicuro e fornisce il mapping tra la chiave ECMA a una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="15b6b-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15b6b-111">Note</span><span class="sxs-lookup"><span data-stu-id="15b6b-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b6b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15b6b-112">Requirements</span></span>  
 <span data-ttu-id="15b6b-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15b6b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b6b-114">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="15b6b-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15b6b-115">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15b6b-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15b6b-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b6b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
