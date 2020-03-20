---
title: Metodo IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175759"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="898f0-102">Metodo IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="898f0-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="898f0-103">Crea una definizione di tipo per un tipo Common Language Runtime e ottiene un token di metadati per tale definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="898f0-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="898f0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="898f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="898f0-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="898f0-106">[in] Nome del tipo in Unicode.</span><span class="sxs-lookup"><span data-stu-id="898f0-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="898f0-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="898f0-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="898f0-108">Si tratta di `CoreTypeAttr` una maschera di bit di valori.</span><span class="sxs-lookup"><span data-stu-id="898f0-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="898f0-109">[in] Token della classe base.</span><span class="sxs-lookup"><span data-stu-id="898f0-109">[in] The token of the base class.</span></span> <span data-ttu-id="898f0-110">Deve essere un `mdTypeDef` o `mdTypeRef` un token.</span><span class="sxs-lookup"><span data-stu-id="898f0-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="898f0-111">[in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="898f0-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="898f0-112">[fuori] Token `mdTypeDef` assegnato.</span><span class="sxs-lookup"><span data-stu-id="898f0-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="898f0-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="898f0-113">Remarks</span></span>  
 <span data-ttu-id="898f0-114">Un flag `dwTypeDefFlags` in specifica se il tipo creato è un tipo di riferimento del sistema di tipi comune (classe o interfaccia) o un tipo di valore di sistema di tipo comune.</span><span class="sxs-lookup"><span data-stu-id="898f0-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="898f0-115">A seconda dei parametri forniti, questo metodo, come effetto `mdInterfaceImpl` collaterale, può anche creare un record per ogni interfaccia ereditata o implementata da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="898f0-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="898f0-116">Tuttavia, questo metodo non `mdInterfaceImpl` restituisce nessuno di questi token.</span><span class="sxs-lookup"><span data-stu-id="898f0-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="898f0-117">Se un client desidera aggiungere `mdInterfaceImpl` o modificare un `IMetaDataImport` token in un secondo momento, deve utilizzare l'interfaccia per enumerarli.</span><span class="sxs-lookup"><span data-stu-id="898f0-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="898f0-118">Se si desidera utilizzare la `[default]` semantica COM dell'interfaccia, è necessario `rtkImplements`fornire l'interfaccia predefinita come primo elemento in ; un attributo personalizzato impostato sulla classe indicherà che la classe dispone `mdInterfaceImpl` di un'interfaccia predefinita (che si presuppone sempre essere il primo token dichiarato per la classe).</span><span class="sxs-lookup"><span data-stu-id="898f0-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="898f0-119">Ogni elemento `rtkImplements` della matrice `mdTypeDef` `mdTypeRef` contiene un o token.</span><span class="sxs-lookup"><span data-stu-id="898f0-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="898f0-120">L'ultimo elemento nella `mdTokenNil`matrice deve essere .</span><span class="sxs-lookup"><span data-stu-id="898f0-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898f0-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="898f0-121">Requirements</span></span>  
 <span data-ttu-id="898f0-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="898f0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898f0-123">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="898f0-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="898f0-124">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="898f0-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="898f0-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898f0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898f0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="898f0-126">See also</span></span>

- [<span data-ttu-id="898f0-127">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="898f0-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="898f0-128">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="898f0-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
