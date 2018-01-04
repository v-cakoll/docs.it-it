---
title: Metodo IMetaDataImport::ResolveTypeRef
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResolveTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64a783297b27c9d1400670eecb7dfe4cb69c2b96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="654a9-102">Metodo IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="654a9-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="654a9-103">Risolve un <xref:System.Type> riferimento rappresentato dal token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="654a9-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="654a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="654a9-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="654a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="654a9-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="654a9-106">[in] Il token di metadati TypeRef per restituire le informazioni di riferimento di tipo per.</span><span class="sxs-lookup"><span data-stu-id="654a9-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="654a9-107">[in] IID dell'interfaccia da restituire `ppIScope`.</span><span class="sxs-lookup"><span data-stu-id="654a9-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="654a9-108">In genere, questo potrebbe essere IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="654a9-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="654a9-109">[out] Interfaccia per l'ambito del modulo in cui è definito il tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="654a9-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="654a9-110">[out] Puntatore a un token TypeDef che rappresenta il tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="654a9-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="654a9-111">Note</span><span class="sxs-lookup"><span data-stu-id="654a9-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="654a9-112">Non utilizzare questo metodo se vengono caricati più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="654a9-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="654a9-113">Il metodo non rispetta i limiti del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="654a9-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="654a9-114">Se più versioni di un assembly vengono caricate e che contengono lo stesso tipo con lo stesso spazio dei nomi, il metodo restituisce l'ambito del modulo del primo tipo trovato.</span><span class="sxs-lookup"><span data-stu-id="654a9-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="654a9-115">Il `ResolveTypeRef` il metodo di ricerca per la definizione del tipo in altri moduli.</span><span class="sxs-lookup"><span data-stu-id="654a9-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="654a9-116">Se viene trovata la definizione del tipo, `ResolveTypeRef` restituisce un'interfaccia per tale ambito del modulo, nonché il token TypeDef per il tipo.</span><span class="sxs-lookup"><span data-stu-id="654a9-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="654a9-117">Se il riferimento al tipo di risoluzione ha un ambito di risoluzione di AssemblyRef, il `ResolveTypeRef` metodo cerca una corrispondenza solo nell'ambito dei metadati che sono già stati aperti mediante chiamate al metodo di [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)metodo o [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="654a9-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="654a9-118">In questo modo `ResolveTypeRef` non può determinare solo dall'AssemblyRef ambito in cui è archiviato l'assembly sul disco o nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="654a9-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="654a9-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="654a9-119">Requirements</span></span>  
 <span data-ttu-id="654a9-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="654a9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="654a9-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="654a9-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="654a9-122">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="654a9-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="654a9-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="654a9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="654a9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="654a9-124">See Also</span></span>  
 [<span data-ttu-id="654a9-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="654a9-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="654a9-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="654a9-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
