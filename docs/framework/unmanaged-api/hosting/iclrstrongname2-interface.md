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
ms.workload: dotnet
ms.openlocfilehash: d4e1274f675ae9289faa6c530d34cd61d033aa07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="f78e1-102">Interfaccia ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="f78e1-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="f78e1-103">Fornisce la possibilità di creare nomi sicuri tramite il gruppo di SHA-2 degli algoritmi di Hash di protezione (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="f78e1-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f78e1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f78e1-104">Methods</span></span>  
  
|<span data-ttu-id="f78e1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f78e1-105">Method</span></span>|<span data-ttu-id="f78e1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f78e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f78e1-107">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="f78e1-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="f78e1-108">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="f78e1-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="f78e1-109">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="f78e1-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="f78e1-110">Verifica la firma di un assembly con nome sicuro e fornisce il mapping tra la chiave ECMA a una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="f78e1-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f78e1-111">Note</span><span class="sxs-lookup"><span data-stu-id="f78e1-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f78e1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f78e1-112">Requirements</span></span>  
 <span data-ttu-id="f78e1-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f78e1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f78e1-114">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="f78e1-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f78e1-115">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f78e1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f78e1-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f78e1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
