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
ms.openlocfilehash: 45f40dcd419e8e2fdf8a3349ccc9461854ad9aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175733"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="f05d4-102">Metodo IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="f05d4-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="f05d4-103">Elimina i metadati di mapping PInvoke per l'oggetto a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="f05d4-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f05d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f05d4-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f05d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f05d4-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f05d4-106">[in] O `mdFieldDef` `mdMethodDef` token che rappresenta l'oggetto per il quale eliminare i metadati del mapping PInvoke.</span><span class="sxs-lookup"><span data-stu-id="f05d4-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f05d4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f05d4-107">Requirements</span></span>  
 <span data-ttu-id="f05d4-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f05d4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f05d4-109">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f05d4-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f05d4-110">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f05d4-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f05d4-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f05d4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05d4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f05d4-112">See also</span></span>

- [<span data-ttu-id="f05d4-113">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f05d4-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f05d4-114">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f05d4-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
