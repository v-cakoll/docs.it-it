---
title: Metodo IMetaDataEmit::DeleteFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 6d0f9a8c5c3baf7594e098a3d5544bad55fdc917
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009288"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="126f0-102">Metodo IMetaDataEmit::DeleteFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="126f0-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="126f0-103">Elimina la firma dei metadati di marshalling PInvoke per l'oggetto a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="126f0-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="126f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="126f0-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="126f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="126f0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="126f0-106">in `mdFieldDef`Token o `mdParamDef` che rappresenta il campo o il parametro per il quale eliminare la firma dei metadati di marshalling.</span><span class="sxs-lookup"><span data-stu-id="126f0-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="126f0-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="126f0-107">Requirements</span></span>  
 <span data-ttu-id="126f0-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="126f0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="126f0-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="126f0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="126f0-110">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="126f0-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="126f0-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="126f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126f0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="126f0-112">See also</span></span>

- [<span data-ttu-id="126f0-113">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="126f0-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="126f0-114">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="126f0-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
