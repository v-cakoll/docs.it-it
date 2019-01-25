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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c69c67c5c9d996bd746d82ea86caf4a396c0b10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625237"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="84272-102">Metodo IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="84272-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="84272-103">Risolve un <xref:System.Type> riferimento rappresentato dal token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="84272-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84272-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84272-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84272-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84272-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="84272-106">[in] Il token di metadati TypeRef per restituire informazioni sul tipo di riferimento per.</span><span class="sxs-lookup"><span data-stu-id="84272-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="84272-107">[in] IID dell'interfaccia da restituire `ppIScope`.</span><span class="sxs-lookup"><span data-stu-id="84272-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="84272-108">In genere, questa sarebbe IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="84272-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="84272-109">[out] Interfaccia per l'ambito del modulo in cui è definito il tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="84272-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="84272-110">[out] Puntatore a un token TypeDef che rappresenta il tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="84272-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84272-111">Note</span><span class="sxs-lookup"><span data-stu-id="84272-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84272-112">Non utilizzare questo metodo se sono caricati più domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="84272-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="84272-113">Il metodo non rispetta i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="84272-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="84272-114">Se sono caricate più versioni di un assembly e che contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.</span><span class="sxs-lookup"><span data-stu-id="84272-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="84272-115">Il `ResolveTypeRef` metodo cerca la definizione del tipo in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="84272-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="84272-116">Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia per tale ambito di modulo, nonché il token TypeDef per il tipo.</span><span class="sxs-lookup"><span data-stu-id="84272-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="84272-117">Se il riferimento al tipo da risolvere dispone di un ambito di risoluzione di AssemblyRef, il `ResolveTypeRef` metodo cerca una corrispondenza solo negli ambiti dei metadati che sono già stati aperti mediante chiamate al metodo il [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)metodo o la [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="84272-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="84272-118">Infatti, `ResolveTypeRef` non è possibile stabilire dal solo nell'ambito di AssemblyRef in cui è archiviato l'assembly sul disco o nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="84272-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84272-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84272-119">Requirements</span></span>  
 <span data-ttu-id="84272-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84272-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84272-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="84272-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84272-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="84272-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84272-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84272-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84272-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84272-124">See also</span></span>
- [<span data-ttu-id="84272-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="84272-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="84272-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="84272-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
