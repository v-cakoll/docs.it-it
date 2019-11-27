---
title: Metodo IMetaDataImport::ResolveTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
ms.openlocfilehash: 800b15bb75e74898cee9d838900ea14b60620940
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431467"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="bb186-102">Metodo IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="bb186-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="bb186-103">Risolve un riferimento <xref:System.Type> rappresentato dal token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="bb186-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb186-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb186-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb186-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb186-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="bb186-106">in Token di metadati TypeRef per cui restituire le informazioni sul tipo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="bb186-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="bb186-107">in IID dell'interfaccia da restituire in `ppIScope`.</span><span class="sxs-lookup"><span data-stu-id="bb186-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="bb186-108">In genere, questo IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="bb186-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="bb186-109">out Interfaccia per l'ambito del modulo in cui è definito il tipo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="bb186-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="bb186-110">out Puntatore a un token TypeDef che rappresenta il tipo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="bb186-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb186-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bb186-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bb186-112">Non usare questo metodo se vengono caricati più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb186-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="bb186-113">Il metodo non rispetta i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb186-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="bb186-114">Se vengono caricate più versioni di un assembly e contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.</span><span class="sxs-lookup"><span data-stu-id="bb186-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="bb186-115">Il metodo `ResolveTypeRef` cerca la definizione del tipo in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="bb186-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="bb186-116">Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia a tale ambito del modulo e il token TypeDef per il tipo.</span><span class="sxs-lookup"><span data-stu-id="bb186-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="bb186-117">Se il riferimento al tipo da risolvere ha un ambito di risoluzione di AssemblyRef, il metodo `ResolveTypeRef` cerca una corrispondenza solo negli ambiti dei metadati già aperti con le chiamate al metodo [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) o [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb186-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="bb186-118">Ciò è dovuto al fatto che `ResolveTypeRef` non è in grado di determinare solo dall'ambito AssemblyRef in cui è archiviato su disco o nel Global Assembly Cache assembly.</span><span class="sxs-lookup"><span data-stu-id="bb186-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb186-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb186-119">Requirements</span></span>  
 <span data-ttu-id="bb186-120">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb186-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb186-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bb186-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb186-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bb186-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb186-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb186-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb186-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb186-124">See also</span></span>

- [<span data-ttu-id="bb186-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bb186-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bb186-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bb186-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
