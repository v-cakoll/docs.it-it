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
ms.openlocfilehash: 371eed84883e2816892c0a6a212a4a89a287cc58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445273"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="9fc7a-102">Metodo IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="9fc7a-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="9fc7a-103">Imposta l'indirizzo virtuale relativo del metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="9fc7a-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fc7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fc7a-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fc7a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9fc7a-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="9fc7a-106">[in] Il token per l'implementazione del metodo o il metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9fc7a-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="9fc7a-107">[in] L'indirizzo dell'area di codice o i dati.</span><span class="sxs-lookup"><span data-stu-id="9fc7a-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fc7a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9fc7a-108">Requirements</span></span>  
 <span data-ttu-id="9fc7a-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fc7a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fc7a-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9fc7a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9fc7a-111">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9fc7a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fc7a-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fc7a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc7a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fc7a-113">See Also</span></span>  
 [<span data-ttu-id="9fc7a-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9fc7a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9fc7a-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9fc7a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
