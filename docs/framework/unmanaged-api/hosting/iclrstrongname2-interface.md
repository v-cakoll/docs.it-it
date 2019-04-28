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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763724"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="aa819-102">Interfaccia ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="aa819-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="aa819-103">Offre la possibilità di creare i nomi sicuri usando il gruppo di SHA-2 di algoritmi Secure Hash (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="aa819-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa819-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="aa819-104">Methods</span></span>  
  
|<span data-ttu-id="aa819-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="aa819-105">Method</span></span>|<span data-ttu-id="aa819-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa819-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa819-107">Metodo StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="aa819-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="aa819-108">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.</span><span class="sxs-lookup"><span data-stu-id="aa819-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="aa819-109">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="aa819-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="aa819-110">Verifica la firma di un assembly con nome sicuro e fornisce un mapping tra la chiave ECMA e una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="aa819-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa819-111">Note</span><span class="sxs-lookup"><span data-stu-id="aa819-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa819-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa819-112">Requirements</span></span>  
 <span data-ttu-id="aa819-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa819-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa819-114">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="aa819-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aa819-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aa819-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa819-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa819-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
