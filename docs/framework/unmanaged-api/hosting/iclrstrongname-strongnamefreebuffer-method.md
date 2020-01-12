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
ms.openlocfilehash: 9aeac02e865214db8fec25621f1bf204a93b36f6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901144"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="716cf-102">Metodo ICLRStrongName::StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="716cf-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="716cf-103">Libera la memoria allocata con una precedente chiamata a un metodo con nome sicuro, ad esempio [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)o [ICLRStrongName:: StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="716cf-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="716cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="716cf-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="716cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="716cf-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="716cf-106">in Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="716cf-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="716cf-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="716cf-107">Return Value</span></span>  
 <span data-ttu-id="716cf-108">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="716cf-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="716cf-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="716cf-109">Requirements</span></span>  
 <span data-ttu-id="716cf-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="716cf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716cf-111">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="716cf-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="716cf-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="716cf-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="716cf-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="716cf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716cf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="716cf-114">See also</span></span>

- [<span data-ttu-id="716cf-115">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="716cf-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
