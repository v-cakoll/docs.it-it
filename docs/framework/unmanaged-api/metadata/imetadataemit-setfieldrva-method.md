---
title: Metodo IMetaDataEmit::SetFieldRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfc4ac58785b766e74d836fa3cf3b1aca75f01d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521023"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="74eff-102">Metodo IMetaDataEmit::SetFieldRVA</span><span class="sxs-lookup"><span data-stu-id="74eff-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="74eff-103">Imposta un valore della variabile globale per l'indirizzo virtuale relativo del campo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="74eff-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74eff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74eff-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74eff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74eff-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="74eff-106">[in] Il token per il campo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="74eff-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="74eff-107">[in] L'indirizzo di un'area dati o codice.</span><span class="sxs-lookup"><span data-stu-id="74eff-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74eff-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74eff-108">Requirements</span></span>  
 <span data-ttu-id="74eff-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74eff-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74eff-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74eff-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74eff-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="74eff-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74eff-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74eff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74eff-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74eff-113">See also</span></span>
- [<span data-ttu-id="74eff-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="74eff-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="74eff-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="74eff-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
