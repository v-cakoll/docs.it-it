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
ms.openlocfilehash: 2facc63023a20dd6aaac64d7d036324c31658bc8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501313"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="71e97-102">Metodo IMetaDataEmit::DefineImportMember</span><span class="sxs-lookup"><span data-stu-id="71e97-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="71e97-103">Crea un riferimento al membro specificato di un tipo o di un modulo definito al di fuori dell'ambito corrente e definisce un token per il riferimento.</span><span class="sxs-lookup"><span data-stu-id="71e97-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71e97-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="71e97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71e97-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="71e97-106">in Interfaccia [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) che rappresenta l'assembly da cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71e97-106">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="71e97-107">in Matrice contenente l'hash per l'assembly specificato da `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="71e97-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="71e97-108">[in] Numero di byte nella matrice di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="71e97-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="71e97-109">in Interfaccia [IMetaDataImport](imetadataimport-interface.md) che rappresenta l'ambito dei metadati da cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71e97-109">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="71e97-110">in Token di metadati che specifica il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71e97-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="71e97-111">Il token può essere un `mdMethodDef` (per un metodo membro), `mdProperty` (per una proprietà del membro) o `mdFieldDef` (per un campo del membro).</span><span class="sxs-lookup"><span data-stu-id="71e97-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="71e97-112">in Interfaccia [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) che rappresenta l'assembly in cui viene importato il membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71e97-112">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="71e97-113">in `mdTypeRef`Token o `mdModuleRef` per il tipo o il modulo, rispettivamente, proprietario del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71e97-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="71e97-114">out `mdMemberRef`Token definito nell'ambito corrente per il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="71e97-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71e97-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="71e97-115">Remarks</span></span>  
 <span data-ttu-id="71e97-116">Il `DefineImportMember` metodo cerca il membro, specificato da `mbMember` , che è definito in un altro ambito, specificato da `pImport` , e ne recupera le proprietà.</span><span class="sxs-lookup"><span data-stu-id="71e97-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="71e97-117">Usa queste informazioni per chiamare il metodo [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md) nell'ambito corrente per creare il riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="71e97-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="71e97-118">In genere, prima di usare il `DefineImportMember` metodo, è necessario creare, nell'ambito corrente, un riferimento al tipo o un riferimento al modulo per la classe, l'interfaccia o il modulo padre del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="71e97-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="71e97-119">Il token di metadati per il riferimento viene quindi passato nell' `tkParent` argomento.</span><span class="sxs-lookup"><span data-stu-id="71e97-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="71e97-120">Non è necessario creare un riferimento all'elemento padre del membro di destinazione se verrà risolto in un secondo momento dal compilatore o dal linker.</span><span class="sxs-lookup"><span data-stu-id="71e97-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="71e97-121">Per concludere:</span><span class="sxs-lookup"><span data-stu-id="71e97-121">To summarize:</span></span>  
  
- <span data-ttu-id="71e97-122">Se il membro di destinazione è un campo o un metodo, usare il metodo [IMetaDataEmit::D efinetyperefbyname](imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md) per creare un riferimento al tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.</span><span class="sxs-lookup"><span data-stu-id="71e97-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="71e97-123">Se il membro di destinazione è una variabile globale o una funzione globale (ovvero non è un membro di una classe o di un'interfaccia), usare il metodo [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) per creare un riferimento al modulo nell'ambito corrente per il modulo padre del membro.</span><span class="sxs-lookup"><span data-stu-id="71e97-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="71e97-124">Se il padre del membro di destinazione verrà risolto in un secondo momento dal compilatore o dal linker, passare `mdTokenNil` `tkParent` .</span><span class="sxs-lookup"><span data-stu-id="71e97-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="71e97-125">L'unico scenario in cui si applica si verifica quando una funzione globale o una variabile globale viene importata da un file con estensione obj che verrà infine collegato al modulo corrente e i metadati vengono uniti.</span><span class="sxs-lookup"><span data-stu-id="71e97-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e97-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71e97-126">Requirements</span></span>  
 <span data-ttu-id="71e97-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71e97-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e97-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="71e97-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71e97-129">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71e97-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71e97-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e97-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e97-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71e97-131">See also</span></span>

- [<span data-ttu-id="71e97-132">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="71e97-132">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="71e97-133">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="71e97-133">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
