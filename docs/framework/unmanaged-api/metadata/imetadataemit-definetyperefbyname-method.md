---
title: Metodo IMetaDataEmit::DefineTypeRefByName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ce04733fa9f149f155d850c53b65b263943cf8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="1dce8-102">Metodo IMetaDataEmit::DefineTypeRefByName</span><span class="sxs-lookup"><span data-stu-id="1dce8-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="1dce8-103">Ottiene i metadati di un token per un tipo definito nell'ambito specificato, che è esterno all'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="1dce8-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dce8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1dce8-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1dce8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1dce8-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="1dce8-106">[in] Il token che specifica l'ambito di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="1dce8-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="1dce8-107">I tipi di token seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="1dce8-107">The following token types are valid:</span></span>  
  
-   <span data-ttu-id="1dce8-108">`mdModuleRef`, se il tipo è definito nello stesso assembly in cui è definito il chiamante.</span><span class="sxs-lookup"><span data-stu-id="1dce8-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="1dce8-109">`mdAssemblyRef`, se il tipo è definito in un assembly diverso da quello in cui è definito il chiamante.</span><span class="sxs-lookup"><span data-stu-id="1dce8-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="1dce8-110">`mdTypeRef`, se il tipo è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="1dce8-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
-   <span data-ttu-id="1dce8-111">`mdModule`, se il tipo è definito nello stesso modulo in cui è definito il chiamante.</span><span class="sxs-lookup"><span data-stu-id="1dce8-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="1dce8-112">Null se il tipo è definito a livello globale.</span><span class="sxs-lookup"><span data-stu-id="1dce8-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="1dce8-113">[in] Il nome del tipo di destinazione in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="1dce8-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="1dce8-114">[out] Un puntatore al `mdTypeRef` token assegnato al tipo.</span><span class="sxs-lookup"><span data-stu-id="1dce8-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dce8-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1dce8-115">Requirements</span></span>  
 <span data-ttu-id="1dce8-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dce8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dce8-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1dce8-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1dce8-118">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1dce8-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1dce8-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dce8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dce8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dce8-120">See Also</span></span>  
 [<span data-ttu-id="1dce8-121">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1dce8-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="1dce8-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1dce8-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
