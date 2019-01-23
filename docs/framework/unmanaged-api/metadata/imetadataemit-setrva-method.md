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
ms.openlocfilehash: 89475ebc5ef04c8693adb7a83bd1dd07f5774fb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544694"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="5809d-102">Metodo IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="5809d-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="5809d-103">Imposta l'indirizzo virtuale relativo del metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="5809d-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5809d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5809d-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5809d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5809d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="5809d-106">[in] Il token per il metodo di destinazione o l'implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="5809d-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="5809d-107">[in] L'indirizzo dell'area dati o codice.</span><span class="sxs-lookup"><span data-stu-id="5809d-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5809d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5809d-108">Requirements</span></span>  
 <span data-ttu-id="5809d-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5809d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5809d-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5809d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5809d-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5809d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5809d-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5809d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5809d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5809d-113">See also</span></span>
- [<span data-ttu-id="5809d-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5809d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5809d-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5809d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
