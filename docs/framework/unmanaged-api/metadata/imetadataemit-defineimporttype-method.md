---
title: Metodo IMetaDataEmit::DefineImportType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4b19b291917b0b507f03c66a358b725a29234f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="f63cf-102">Metodo IMetaDataEmit::DefineImportType</span><span class="sxs-lookup"><span data-stu-id="f63cf-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="f63cf-103">Crea un riferimento al tipo specificato definito all'esterno dell'ambito corrente e definisce un token per tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="f63cf-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f63cf-104">Syntax</span></span>  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f63cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f63cf-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="f63cf-106">[in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia che rappresenta l'assembly dal quale viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f63cf-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f63cf-107">[in] Matrice che contiene l'hash per l'assembly specificato da `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="f63cf-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f63cf-108">[in] Numero di byte nella matrice di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="f63cf-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="f63cf-109">[in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia che rappresenta l'ambito dei metadati dal quale viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f63cf-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="f63cf-110">[in] Un `mdTypeDef` token che specifica il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f63cf-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="f63cf-111">[in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaccia che rappresenta l'assembly in cui viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f63cf-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="f63cf-112">[out] Il `mdTypeRef` token definito nell'ambito corrente per il riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="f63cf-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f63cf-113">Note</span><span class="sxs-lookup"><span data-stu-id="f63cf-113">Remarks</span></span>  
 <span data-ttu-id="f63cf-114">Prima di chiamare il [IMetaDataEmit:: DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) (metodo), è possibile utilizzare il `DefineImportType` metodo per creare un riferimento al tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.</span><span class="sxs-lookup"><span data-stu-id="f63cf-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f63cf-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f63cf-115">Requirements</span></span>  
 <span data-ttu-id="f63cf-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f63cf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f63cf-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f63cf-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f63cf-118">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f63cf-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f63cf-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f63cf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f63cf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f63cf-120">See Also</span></span>  
 [<span data-ttu-id="f63cf-121">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f63cf-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f63cf-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f63cf-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
