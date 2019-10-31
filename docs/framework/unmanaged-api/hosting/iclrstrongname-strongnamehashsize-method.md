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
ms.openlocfilehash: 8db3b1854e334cef4d91d21eb5f666ba2e88fc2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135055"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="79b45-102">Metodo ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="79b45-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="79b45-103">Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="79b45-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79b45-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79b45-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79b45-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="79b45-106">in Algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="79b45-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="79b45-107">out Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="79b45-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79b45-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="79b45-108">Return Value</span></span>  
 <span data-ttu-id="79b45-109">`S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="79b45-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b45-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79b45-110">Requirements</span></span>  
 <span data-ttu-id="79b45-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79b45-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79b45-112">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="79b45-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="79b45-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="79b45-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79b45-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79b45-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b45-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79b45-115">See also</span></span>

- [<span data-ttu-id="79b45-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="79b45-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
