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
ms.openlocfilehash: 0f4fdcbdfb9db7664920a42b9406a58f9c2de0b8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763111"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="e290c-102">Metodo ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="e290c-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="e290c-103">Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="e290c-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e290c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e290c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e290c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e290c-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="e290c-106">in Algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="e290c-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e290c-107">out Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="e290c-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e290c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e290c-108">Return Value</span></span>  
 <span data-ttu-id="e290c-109">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="e290c-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e290c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e290c-110">Requirements</span></span>  
 <span data-ttu-id="e290c-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e290c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e290c-112">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e290c-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e290c-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e290c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e290c-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e290c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e290c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e290c-115">See also</span></span>

- [<span data-ttu-id="e290c-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e290c-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
