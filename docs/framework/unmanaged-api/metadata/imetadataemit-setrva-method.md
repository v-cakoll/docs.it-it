---
title: Metodo IMetaDataEmit::SetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a9df30ae11b13c052c75b05b0850d9f4754620
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470094"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="a1bb3-102">Metodo IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="a1bb3-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="a1bb3-103">Imposta l'indirizzo virtuale relativo del metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="a1bb3-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1bb3-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1bb3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1bb3-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a1bb3-106">[in] Il token per il metodo di destinazione o l'implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="a1bb3-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="a1bb3-107">[in] L'indirizzo dell'area dati o codice.</span><span class="sxs-lookup"><span data-stu-id="a1bb3-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bb3-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1bb3-108">Requirements</span></span>  
 <span data-ttu-id="a1bb3-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1bb3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bb3-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a1bb3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1bb3-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a1bb3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1bb3-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bb3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bb3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1bb3-113">See also</span></span>
- [<span data-ttu-id="a1bb3-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a1bb3-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a1bb3-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a1bb3-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
