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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78f2405bba9172b775b01e5417860c3f3d2dd4a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206928"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="126f0-102">Metodo IMetaDataEmit::DeleteFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="126f0-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="126f0-103">Elimina definitivamente i PInvoke marshalling firma dei metadati per l'oggetto fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="126f0-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="126f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="126f0-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="126f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="126f0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="126f0-106">[in] Un' `mdFieldDef` o `mdParamDef` token che rappresenta il campo o un parametro per cui si desidera eliminare la firma dei metadati del marshalling.</span><span class="sxs-lookup"><span data-stu-id="126f0-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="126f0-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="126f0-107">Requirements</span></span>  
 <span data-ttu-id="126f0-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="126f0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="126f0-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="126f0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="126f0-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="126f0-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="126f0-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="126f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126f0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="126f0-112">See also</span></span>

- [<span data-ttu-id="126f0-113">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="126f0-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="126f0-114">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="126f0-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
