---
title: Metodo IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 596888a8eb4a55c4cfe594b1911f17f6d32f56d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165932"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="1bbdf-102">Metodo IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="1bbdf-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="1bbdf-103">Imposta le funzionalità di un tipo definito da una chiamata precedente a [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="1bbdf-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bbdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bbdf-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bbdf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1bbdf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1bbdf-106">[in] Un' `mdTypeDef` token ottenuto dalla chiamata originale a [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="1bbdf-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="1bbdf-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="1bbdf-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="1bbdf-108">Si tratta di una maschera di bit delle `CorTypeAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="1bbdf-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="1bbdf-109">[in] Il `mdToken` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="1bbdf-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="1bbdf-110">Ottenuto da una chiamata precedente a [DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), o `null`.</span><span class="sxs-lookup"><span data-stu-id="1bbdf-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="1bbdf-111">[in] Matrice dei token per le interfacce implementate da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="1bbdf-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="1bbdf-112">Questi `mdTypeRef` i token vengano ottenuti utilizzando [DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="1bbdf-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="1bbdf-113">È l'ultimo elemento della matrice deve essere `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="1bbdf-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bbdf-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bbdf-114">Requirements</span></span>  
 <span data-ttu-id="1bbdf-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bbdf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bbdf-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1bbdf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1bbdf-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1bbdf-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bbdf-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bbdf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbdf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bbdf-119">See also</span></span>

- [<span data-ttu-id="1bbdf-120">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1bbdf-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1bbdf-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1bbdf-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
