---
title: Metodo IMetaDataEmit::SetTypeDefProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 50f92d0ff307621695887ee7a0af2d4d19985f51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="0f8c7-102">Metodo IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="0f8c7-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="0f8c7-103">Imposta le funzionalità di un tipo definito da una precedente chiamata a [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f8c7-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f8c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f8c7-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f8c7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f8c7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0f8c7-106">[in] Un `mdTypeDef` token ottenuto dalla chiamata originale a [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f8c7-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="0f8c7-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="0f8c7-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="0f8c7-108">Si tratta di una maschera di bit di `CorTypeAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="0f8c7-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="0f8c7-109">[in] Il `mdToken` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="0f8c7-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="0f8c7-110">Ottenuto da una precedente chiamata a [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), o `null`.</span><span class="sxs-lookup"><span data-stu-id="0f8c7-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="0f8c7-111">[in] Matrice di token per le interfacce implementate da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="0f8c7-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="0f8c7-112">Questi `mdTypeRef` token vengono ottenuti tramite [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f8c7-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="0f8c7-113">Deve essere l'ultimo elemento della matrice è `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="0f8c7-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f8c7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f8c7-114">Requirements</span></span>  
 <span data-ttu-id="0f8c7-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f8c7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f8c7-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0f8c7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f8c7-117">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f8c7-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f8c7-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f8c7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f8c7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f8c7-119">See Also</span></span>  
 [<span data-ttu-id="0f8c7-120">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="0f8c7-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0f8c7-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0f8c7-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
