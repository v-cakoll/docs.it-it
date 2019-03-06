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
ms.openlocfilehash: 7ac44d29dd99e0205c515905f9846263033babf3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479298"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="83fdf-102">Metodo IMetaDataEmit::DefineImportMember</span><span class="sxs-lookup"><span data-stu-id="83fdf-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="83fdf-103">Crea un riferimento al membro specificato di un tipo o un modulo che viene definita all'esterno dell'ambito corrente e definisce un token per tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="83fdf-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83fdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83fdf-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="83fdf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83fdf-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="83fdf-106">[in] Un' [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia che rappresenta l'assembly dal quale viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fdf-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="83fdf-107">[in] Matrice che contiene il valore hash per l'assembly specificato da `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="83fdf-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="83fdf-108">[in] Numero di byte nella matrice di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="83fdf-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="83fdf-109">[in] Un' [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia che rappresenta l'ambito dei metadati dal quale viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fdf-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="83fdf-110">[in] Il token di metadati che specifica il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fdf-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="83fdf-111">Il token può essere un' `mdMethodDef` (per un metodo del membro), `mdProperty` (per una proprietà del membro), o `mdFieldDef` (per un campo membro) token.</span><span class="sxs-lookup"><span data-stu-id="83fdf-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="83fdf-112">[in] Un' [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaccia che rappresenta l'assembly in cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fdf-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="83fdf-113">[in] Il `mdTypeRef` o `mdModuleRef` per il tipo o il modulo, rispettivamente, il proprietario del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fdf-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="83fdf-114">[out] Il `mdMemberRef` token definito nell'ambito corrente per il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="83fdf-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83fdf-115">Note</span><span class="sxs-lookup"><span data-stu-id="83fdf-115">Remarks</span></span>  
 <span data-ttu-id="83fdf-116">Il `DefineImportMember` metodo cerca il membro, specificato da `mbMember`, che viene definito in un altro ambito, specificato da `pImport`e recupera le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="83fdf-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="83fdf-117">Questa informazione viene utilizzata per chiamare il [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) metodo nell'ambito corrente per creare il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="83fdf-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="83fdf-118">In genere, prima di utilizzare il `DefineImportMember` metodo, è necessario creare, nell'ambito corrente, un riferimento al tipo o un riferimento di modulo per modulo, interfaccia o classe padre del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fdf-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="83fdf-119">Il token di metadati per questo riferimento viene quindi passato nel `tkParent` argomento.</span><span class="sxs-lookup"><span data-stu-id="83fdf-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="83fdf-120">Non devi creare un riferimento all'elemento padre del membro di destinazione se che verrà risolto in un secondo momento dal compilatore o del linker.</span><span class="sxs-lookup"><span data-stu-id="83fdf-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="83fdf-121">Per concludere:</span><span class="sxs-lookup"><span data-stu-id="83fdf-121">To summarize:</span></span>  
  
-   <span data-ttu-id="83fdf-122">Se il membro di destinazione è un campo o un metodo, usare il [DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o il [DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) metodo per creare un riferimento di tipo, nell'ambito corrente, per il classe padre o interfaccia padre del membro.</span><span class="sxs-lookup"><span data-stu-id="83fdf-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
-   <span data-ttu-id="83fdf-123">Se il membro di destinazione è una funzione globale di variabili o globale (vale a dire, non un membro di una classe o interfaccia), usare il [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) metodo per creare un riferimento al modulo, nell'ambito corrente, per padre il membro modulo.</span><span class="sxs-lookup"><span data-stu-id="83fdf-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
-   <span data-ttu-id="83fdf-124">Se l'elemento padre del membro di destinazione verrà risolto in un secondo momento dal compilatore o del linker, passare `mdTokenNil` in `tkParent`.</span><span class="sxs-lookup"><span data-stu-id="83fdf-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="83fdf-125">L'unico scenario in cui si applica è quando una funzione globale o variabile globale viene importato da un file con estensione obj che infine verrà collegato al modulo corrente e i metadati verranno uniti.</span><span class="sxs-lookup"><span data-stu-id="83fdf-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83fdf-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83fdf-126">Requirements</span></span>  
 <span data-ttu-id="83fdf-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83fdf-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83fdf-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83fdf-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83fdf-129">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="83fdf-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83fdf-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83fdf-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83fdf-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83fdf-131">See also</span></span>
- [<span data-ttu-id="83fdf-132">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="83fdf-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="83fdf-133">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="83fdf-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
