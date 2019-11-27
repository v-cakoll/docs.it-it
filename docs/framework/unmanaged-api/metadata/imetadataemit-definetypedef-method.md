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
ms.openlocfilehash: 031996813718a074eebab62ff54a2de52b898c22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450220"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="414cb-102">Metodo IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="414cb-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="414cb-103">Crea una definizione di tipo per un tipo di Common Language Runtime e ottiene un token di metadati per la definizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="414cb-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="414cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="414cb-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="414cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="414cb-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="414cb-106">in Nome del tipo in Unicode.</span><span class="sxs-lookup"><span data-stu-id="414cb-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="414cb-107">[in] attributi `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="414cb-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="414cb-108">Si tratta di una maschera di maschera dei valori `CoreTypeAttr`.</span><span class="sxs-lookup"><span data-stu-id="414cb-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="414cb-109">in Token della classe di base.</span><span class="sxs-lookup"><span data-stu-id="414cb-109">[in] The token of the base class.</span></span> <span data-ttu-id="414cb-110">Deve essere un `mdTypeDef` o un token di `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="414cb-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="414cb-111">in Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="414cb-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="414cb-112">out Token `mdTypeDef` assegnato.</span><span class="sxs-lookup"><span data-stu-id="414cb-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="414cb-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="414cb-113">Remarks</span></span>  
 <span data-ttu-id="414cb-114">Un flag in `dwTypeDefFlags` specifica se il tipo da creare è un tipo di riferimento Common Type System (classe o interfaccia) o un tipo di valore Common Type System.</span><span class="sxs-lookup"><span data-stu-id="414cb-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="414cb-115">A seconda dei parametri forniti, questo metodo, come effetto collaterale, può anche creare un record `mdInterfaceImpl` per ogni interfaccia ereditata o implementata da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="414cb-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="414cb-116">Tuttavia, questo metodo non restituisce alcuno di questi token di `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="414cb-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="414cb-117">Se un client desidera aggiungere o modificare un token di `mdInterfaceImpl` in un secondo momento, è necessario utilizzare l'interfaccia `IMetaDataImport` per enumerarli.</span><span class="sxs-lookup"><span data-stu-id="414cb-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="414cb-118">Se si desidera utilizzare la semantica COM dell'interfaccia `[default]`, è necessario fornire l'interfaccia predefinita come primo elemento nel `rtkImplements`; un attributo personalizzato impostato sulla classe indicherà che la classe dispone di un'interfaccia predefinita (che viene sempre considerata il primo token di `mdInterfaceImpl` dichiarato per la classe).</span><span class="sxs-lookup"><span data-stu-id="414cb-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="414cb-119">Ogni elemento della matrice `rtkImplements` include un token `mdTypeDef` o `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="414cb-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="414cb-120">L'ultimo elemento nella matrice deve essere `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="414cb-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="414cb-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="414cb-121">Requirements</span></span>  
 <span data-ttu-id="414cb-122">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="414cb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="414cb-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="414cb-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="414cb-124">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="414cb-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="414cb-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="414cb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414cb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="414cb-126">See also</span></span>

- [<span data-ttu-id="414cb-127">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="414cb-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="414cb-128">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="414cb-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
