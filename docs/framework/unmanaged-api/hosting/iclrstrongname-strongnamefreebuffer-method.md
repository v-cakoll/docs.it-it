---
title: Metodo ICLRStrongName::StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef8c1e96c12b554a89d012633d1e5c347dab6de4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398524"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="e1314-102">Metodo ICLRStrongName::StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="e1314-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="e1314-103">Libera la memoria allocata con una precedente chiamata a un metodo con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), o [ ICLRStrongName:: StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="e1314-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1314-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1314-104">Syntax</span></span>  
  
```  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1314-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1314-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="e1314-106">[in] Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="e1314-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1314-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1314-107">Return Value</span></span>  
 <span data-ttu-id="e1314-108">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="e1314-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1314-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1314-109">Requirements</span></span>  
 <span data-ttu-id="e1314-110">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1314-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1314-111">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="e1314-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1314-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e1314-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1314-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1314-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1314-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1314-114">See Also</span></span>  
 [<span data-ttu-id="e1314-115">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e1314-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
