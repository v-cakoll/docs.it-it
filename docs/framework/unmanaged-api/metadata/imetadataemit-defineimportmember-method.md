---
title: Metodo IMetaDataEmit::DefineImportMember
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f9995fda70d1d5a3c19c30496de6c32f20015d47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449390"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="3cc0d-102">Metodo IMetaDataEmit::DefineImportMember</span><span class="sxs-lookup"><span data-stu-id="3cc0d-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="3cc0d-103">Crea un riferimento al membro di un tipo o un modulo che viene definito all'esterno dell'ambito corrente, viene definito un token per il riferimento specificato.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc0d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cc0d-104">Syntax</span></span>  
  
```  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cc0d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3cc0d-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="3cc0d-106">[in] Un [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia che rappresenta l'assembly dal quale viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="3cc0d-107">[in] Matrice che contiene l'hash per l'assembly specificato da `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="3cc0d-108">[in] Numero di byte nella matrice di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="3cc0d-109">[in] Un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia che rappresenta l'ambito dei metadati dal quale viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="3cc0d-110">[in] Il token di metadati che specifica il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="3cc0d-111">Il token può essere un `mdMethodDef` (per un metodo di membro), `mdProperty` (per una proprietà del membro), o `mdFieldDef` (per un campo membro) token.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="3cc0d-112">[in] Un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaccia che rappresenta l'assembly in cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="3cc0d-113">[in] Il `mdTypeRef` o `mdModuleRef` per il tipo o il modulo, rispettivamente, il proprietario del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="3cc0d-114">[out] Il `mdMemberRef` token definito nell'ambito corrente per il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cc0d-115">Note</span><span class="sxs-lookup"><span data-stu-id="3cc0d-115">Remarks</span></span>  
 <span data-ttu-id="3cc0d-116">Il `DefineImportMember` metodo cerca il membro, specificato da `mbMember`, che viene definito in un altro ambito, indicato da `pImport`e recupera le proprietà.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="3cc0d-117">Utilizza queste informazioni per chiamare il [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) metodo nell'ambito corrente per creare il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="3cc0d-118">In genere, prima di usare il `DefineImportMember` (metodo), è necessario creare, nell'ambito corrente, un riferimento al tipo o il riferimento al modulo per modulo, interfaccia o classe padre del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="3cc0d-119">Il token di metadati per questo riferimento viene quindi passato il `tkParent` argomento.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="3cc0d-120">Non è necessario creare un riferimento all'elemento padre del membro di destinazione se verrà risolto in un secondo momento dal compilatore o del linker.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="3cc0d-121">Per concludere:</span><span class="sxs-lookup"><span data-stu-id="3cc0d-121">To summarize:</span></span>  
  
-   <span data-ttu-id="3cc0d-122">Se il membro di destinazione è un campo o metodo, utilizzare il [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) metodo per creare un riferimento al tipo, nell'ambito corrente, per il classe padre o interfaccia padre del membro.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
-   <span data-ttu-id="3cc0d-123">Se il membro di destinazione è una funzione globale di variabile o globale (ovvero, non un membro di una classe o interfaccia), utilizzare il [IMetaDataEmit:: DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) metodo per creare un riferimento al modulo, nell'ambito corrente, per padre il membro modulo.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
-   <span data-ttu-id="3cc0d-124">Se l'elemento padre del membro di destinazione verrà risolto in un secondo momento dal compilatore o del linker, passare `mdTokenNil` in `tkParent`.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="3cc0d-125">L'unico scenario in cui si applica è quando una funzione globale o variabile globale viene importata da un file con estensione obj che verrà infine collegato nel modulo corrente e i metadati verranno uniti.</span><span class="sxs-lookup"><span data-stu-id="3cc0d-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cc0d-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3cc0d-126">Requirements</span></span>  
 <span data-ttu-id="3cc0d-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cc0d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cc0d-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3cc0d-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3cc0d-129">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3cc0d-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cc0d-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cc0d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cc0d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cc0d-131">See Also</span></span>  
 [<span data-ttu-id="3cc0d-132">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3cc0d-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="3cc0d-133">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3cc0d-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
