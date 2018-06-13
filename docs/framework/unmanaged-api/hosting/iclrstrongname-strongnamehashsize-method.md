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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ebf2e0225cf497a0b89a46ecdb3e203d5b9a4cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432014"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="14559-102">Metodo ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="14559-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="14559-103">Ottiene le dimensioni del buffer necessarie per generare un hash, utilizzando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="14559-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14559-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14559-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14559-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14559-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="14559-106">[in] L'algoritmo hash utilizzato per calcolare le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="14559-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="14559-107">[out] Dimensioni del buffer restituito, in byte.</span><span class="sxs-lookup"><span data-stu-id="14559-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14559-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="14559-108">Return Value</span></span>  
 <span data-ttu-id="14559-109">`S_OK` Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="14559-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14559-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14559-110">Requirements</span></span>  
 <span data-ttu-id="14559-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14559-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14559-112">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="14559-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="14559-113">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="14559-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14559-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14559-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14559-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14559-115">See Also</span></span>  
 [<span data-ttu-id="14559-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="14559-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
