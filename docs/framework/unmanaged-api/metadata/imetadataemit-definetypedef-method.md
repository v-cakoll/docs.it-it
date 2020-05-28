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
ms.openlocfilehash: dc064b00e32bb6b1d8c2d0c20f571b35919eae23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009340"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="a8946-102">Metodo IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="a8946-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="a8946-103">Crea una definizione di tipo per un tipo di Common Language Runtime e ottiene un token di metadati per la definizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="a8946-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8946-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8946-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8946-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8946-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="a8946-106">in Nome del tipo in Unicode.</span><span class="sxs-lookup"><span data-stu-id="a8946-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="a8946-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="a8946-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="a8946-108">Si tratta di una maschera di maschera di `CoreTypeAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="a8946-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="a8946-109">in Token della classe di base.</span><span class="sxs-lookup"><span data-stu-id="a8946-109">[in] The token of the base class.</span></span> <span data-ttu-id="a8946-110">Deve essere un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="a8946-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="a8946-111">in Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a8946-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="a8946-112">out `mdTypeDef`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="a8946-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8946-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="a8946-113">Remarks</span></span>  
 <span data-ttu-id="a8946-114">Un flag in `dwTypeDefFlags` specifica se il tipo creato è un tipo di riferimento Common Type System (classe o interfaccia) o un tipo di valore Common Type System.</span><span class="sxs-lookup"><span data-stu-id="a8946-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="a8946-115">A seconda dei parametri forniti, questo metodo, come effetto collaterale, può anche creare un `mdInterfaceImpl` record per ogni interfaccia ereditata o implementata da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="a8946-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="a8946-116">Tuttavia, questo metodo non restituisce alcuno di questi `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="a8946-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="a8946-117">Se un client desidera aggiungere o modificare un token in un secondo momento `mdInterfaceImpl` , deve utilizzare l' `IMetaDataImport` interfaccia per enumerarli.</span><span class="sxs-lookup"><span data-stu-id="a8946-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="a8946-118">Se si desidera utilizzare la semantica COM dell' `[default]` interfaccia, è necessario fornire l'interfaccia predefinita come primo elemento in `rtkImplements` ; un attributo personalizzato impostato sulla classe indicherà che la classe dispone di un'interfaccia predefinita (che viene sempre considerata il primo `mdInterfaceImpl` token dichiarato per la classe).</span><span class="sxs-lookup"><span data-stu-id="a8946-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="a8946-119">Ogni elemento della `rtkImplements` matrice include un `mdTypeDef` token o `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="a8946-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="a8946-120">L'ultimo elemento nella matrice deve essere `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="a8946-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8946-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8946-121">Requirements</span></span>  
 <span data-ttu-id="a8946-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8946-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8946-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a8946-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8946-124">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8946-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8946-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8946-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8946-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8946-126">See also</span></span>

- [<span data-ttu-id="a8946-127">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a8946-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a8946-128">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a8946-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
