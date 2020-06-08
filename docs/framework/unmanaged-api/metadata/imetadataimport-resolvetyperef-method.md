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
ms.openlocfilehash: f55af87e21b48430807166cb03e1d41271e830a1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503440"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="a0b4d-102">Metodo IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="a0b4d-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="a0b4d-103">Risolve un <xref:System.Type> riferimento rappresentato dal token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b4d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0b4d-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b4d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0b4d-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="a0b4d-106">in Token di metadati TypeRef per cui restituire le informazioni sul tipo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="a0b4d-107">in IID dell'interfaccia da restituire in `ppIScope` .</span><span class="sxs-lookup"><span data-stu-id="a0b4d-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="a0b4d-108">In genere, questo IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="a0b4d-109">out Interfaccia per l'ambito del modulo in cui è definito il tipo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="a0b4d-110">out Puntatore a un token TypeDef che rappresenta il tipo a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0b4d-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a0b4d-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a0b4d-112">Non usare questo metodo se vengono caricati più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="a0b4d-113">Il metodo non rispetta i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="a0b4d-114">Se vengono caricate più versioni di un assembly e contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="a0b4d-115">Il `ResolveTypeRef` metodo cerca la definizione del tipo in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="a0b4d-116">Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia a tale ambito del modulo e il token typedef per il tipo.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="a0b4d-117">Se il riferimento al tipo da risolvere ha un ambito di risoluzione di AssemblyRef, il `ResolveTypeRef` metodo cerca una corrispondenza solo negli ambiti dei metadati già aperti con le chiamate al metodo [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) o [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a0b4d-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="a0b4d-118">Ciò è dovuto `ResolveTypeRef` al fatto che non è in grado di determinare solo dall'ambito AssemblyRef in cui è archiviato l'assembly su disco o nel Global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="a0b4d-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b4d-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0b4d-119">Requirements</span></span>  
 <span data-ttu-id="a0b4d-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0b4d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b4d-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a0b4d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0b4d-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a0b4d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0b4d-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b4d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b4d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0b4d-124">See also</span></span>

- [<span data-ttu-id="a0b4d-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a0b4d-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a0b4d-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a0b4d-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
