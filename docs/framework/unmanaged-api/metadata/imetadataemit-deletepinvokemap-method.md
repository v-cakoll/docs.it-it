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
ms.openlocfilehash: 79af7b5679598ffa82471dcb69adabc2394b13fa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009301"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="166ce-102">Metodo IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="166ce-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="166ce-103">Elimina i metadati di mapping PInvoke per l'oggetto a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="166ce-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="166ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="166ce-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="166ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="166ce-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="166ce-106">in `mdFieldDef`Token o `mdMethodDef` che rappresenta l'oggetto per il quale eliminare i metadati del mapping PInvoke.</span><span class="sxs-lookup"><span data-stu-id="166ce-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="166ce-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="166ce-107">Requirements</span></span>  
 <span data-ttu-id="166ce-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="166ce-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="166ce-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="166ce-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="166ce-110">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="166ce-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="166ce-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="166ce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166ce-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="166ce-112">See also</span></span>

- [<span data-ttu-id="166ce-113">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="166ce-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="166ce-114">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="166ce-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
