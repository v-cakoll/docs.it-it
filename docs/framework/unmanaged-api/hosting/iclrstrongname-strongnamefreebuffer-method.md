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
ms.openlocfilehash: a08aef367f300f7617e3bc9dc721b904f6f33626
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176357"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="a1f84-102">Metodo ICLRStrongName::StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="a1f84-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="a1f84-103">Libera la memoria allocata con una precedente chiamata a un metodo con nome sicuro, ad esempio [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)o [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1f84-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f84-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1f84-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1f84-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1f84-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="a1f84-106">[in] Un puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="a1f84-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1f84-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1f84-107">Return Value</span></span>  
 <span data-ttu-id="a1f84-108">`S_OK`se il metodo è stato completato correttamente; in caso contrario, un valore HRESULT che indica un errore (vedere [Valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="a1f84-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f84-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1f84-109">Requirements</span></span>  
 <span data-ttu-id="a1f84-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f84-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f84-111">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a1f84-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a1f84-112">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1f84-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1f84-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f84-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1f84-114">See also</span></span>

- [<span data-ttu-id="a1f84-115">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a1f84-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
