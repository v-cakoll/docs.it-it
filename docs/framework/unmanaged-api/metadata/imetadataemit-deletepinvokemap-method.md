---
title: Metodo IMetaDataEmit::DeletePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ea100ff86286cb98db5aa9fa6f3c12f5d318a90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217744"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="bd7aa-102">Metodo IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="bd7aa-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="bd7aa-103">Elimina i metadati di mapping PInvoke per l'oggetto fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd7aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd7aa-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd7aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd7aa-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bd7aa-106">[in] Un' `mdFieldDef` o `mdMethodDef` token che rappresenta l'oggetto per cui si desidera eliminare i metadati di mapping di PInvoke.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd7aa-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd7aa-107">Requirements</span></span>  
 <span data-ttu-id="bd7aa-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd7aa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd7aa-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bd7aa-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd7aa-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bd7aa-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd7aa-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd7aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7aa-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd7aa-112">See also</span></span>

- [<span data-ttu-id="bd7aa-113">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bd7aa-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bd7aa-114">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bd7aa-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
