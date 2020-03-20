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
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175863"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="60f20-102">Metodo IMetaDataEmit::DefineImportMember</span><span class="sxs-lookup"><span data-stu-id="60f20-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="60f20-103">Crea un riferimento al membro specificato di un tipo o modulo definito all'esterno dell'ambito corrente e definisce un token per tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="60f20-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60f20-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60f20-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="60f20-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60f20-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="60f20-106">[in] Interfaccia [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) che rappresenta l'assembly da cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60f20-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="60f20-107">[in] Matrice che contiene l'hash per `pAssemImport`l'assembly specificato da .</span><span class="sxs-lookup"><span data-stu-id="60f20-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="60f20-108">[in] Numero di byte nella matrice di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="60f20-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="60f20-109">[in] Interfaccia [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che rappresenta l'ambito dei metadati da cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60f20-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="60f20-110">[in] Token di metadati che specifica il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60f20-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="60f20-111">Il token può `mdMethodDef` essere un token `mdProperty` (per un metodo `mdFieldDef` membro), (per una proprietà del membro) o (per un campo membro).</span><span class="sxs-lookup"><span data-stu-id="60f20-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="60f20-112">[in] Interfaccia [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) che rappresenta l'assembly in cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60f20-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="60f20-113">[in] Il `mdTypeRef` `mdModuleRef` token o per il tipo o modulo, rispettivamente, che possiede il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60f20-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="60f20-114">[fuori] Token `mdMemberRef` definito nell'ambito corrente per il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="60f20-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60f20-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="60f20-115">Remarks</span></span>  
 <span data-ttu-id="60f20-116">Il `DefineImportMember` metodo cerca il membro `mbMember`, specificato da , definito `pImport`in un altro ambito, specificato da , e ne recupera le proprietà.</span><span class="sxs-lookup"><span data-stu-id="60f20-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="60f20-117">Utilizza queste informazioni per chiamare il metodo [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) nell'ambito corrente per creare il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="60f20-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="60f20-118">In genere, prima `DefineImportMember` di utilizzare il metodo, è necessario creare, nell'ambito corrente, un riferimento al tipo o un riferimento al modulo per la classe padre, l'interfaccia o il modulo del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60f20-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="60f20-119">Il token di metadati per `tkParent` questo riferimento viene quindi passato nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="60f20-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="60f20-120">Non è necessario creare un riferimento all'elemento padre del membro di destinazione se verrà risolto in un secondo momento dal compilatore o dal linker.</span><span class="sxs-lookup"><span data-stu-id="60f20-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="60f20-121">Per riepilogare:</span><span class="sxs-lookup"><span data-stu-id="60f20-121">To summarize:</span></span>  
  
- <span data-ttu-id="60f20-122">Se il membro di destinazione è un campo o un metodo, utilizzare il [Metodo IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) per creare un riferimento al tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.</span><span class="sxs-lookup"><span data-stu-id="60f20-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="60f20-123">Se il membro di destinazione è una variabile globale o una funzione globale, ovvero non è un membro di una classe o di un'interfaccia, utilizzare il metodo [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) per creare un riferimento al modulo, nell'ambito corrente, per il modulo padre del membro.</span><span class="sxs-lookup"><span data-stu-id="60f20-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="60f20-124">Se l'elemento padre del membro di destinazione verrà risolto `mdTokenNil` `tkParent`in un secondo momento dal compilatore o dal linker, passare .</span><span class="sxs-lookup"><span data-stu-id="60f20-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="60f20-125">L'unico scenario in cui questo si applica è quando una funzione globale o una variabile globale viene importata da un file obj che verrà infine collegato nel modulo corrente e i metadati uniti.</span><span class="sxs-lookup"><span data-stu-id="60f20-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60f20-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60f20-126">Requirements</span></span>  
 <span data-ttu-id="60f20-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60f20-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60f20-128">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="60f20-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60f20-129">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60f20-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60f20-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f20-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f20-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60f20-131">See also</span></span>

- [<span data-ttu-id="60f20-132">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="60f20-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="60f20-133">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="60f20-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
