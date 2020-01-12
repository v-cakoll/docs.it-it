---
title: Metodo ICLRStrongName::StrongNameHashSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: abcae4a89dc2ee3895d6ff246fa7358a5fe2f06e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901107"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="e4de4-102">Metodo ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="e4de4-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="e4de4-103">Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="e4de4-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4de4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4de4-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4de4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4de4-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="e4de4-106">in Algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="e4de4-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e4de4-107">out Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="e4de4-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4de4-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e4de4-108">Return Value</span></span>  
 <span data-ttu-id="e4de4-109">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="e4de4-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4de4-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e4de4-110">Requirements</span></span>  
 <span data-ttu-id="e4de4-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4de4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4de4-112">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e4de4-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e4de4-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e4de4-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4de4-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4de4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4de4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4de4-115">See also</span></span>

- [<span data-ttu-id="e4de4-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e4de4-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
