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
ms.openlocfilehash: 02331bb3b0c70b946eaa28c9cd316f109ac927b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777231"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="1824b-102">Metodo IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="1824b-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="1824b-103">Imposta l'indirizzo virtuale relativo del metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="1824b-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1824b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1824b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1824b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1824b-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="1824b-106">[in] Il token per il metodo di destinazione o l'implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="1824b-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="1824b-107">[in] L'indirizzo dell'area dati o codice.</span><span class="sxs-lookup"><span data-stu-id="1824b-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1824b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1824b-108">Requirements</span></span>  
 <span data-ttu-id="1824b-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1824b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1824b-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1824b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1824b-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1824b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1824b-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1824b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1824b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1824b-113">See also</span></span>

- [<span data-ttu-id="1824b-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1824b-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1824b-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1824b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
