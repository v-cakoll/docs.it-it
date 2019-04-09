---
title: Metodo IMetaDataEmit::DefineTypeRefByName
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d93c55cec3d35fd4208a4a8a7c9b235dd10fb9ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156169"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="9dd34-102">Metodo IMetaDataEmit::DefineTypeRefByName</span><span class="sxs-lookup"><span data-stu-id="9dd34-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="9dd34-103">Ottiene i metadati di un token per un tipo definito nell'ambito specificato, che non rientrano nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="9dd34-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dd34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dd34-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dd34-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9dd34-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="9dd34-106">[in] Il token che specifica l'ambito di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="9dd34-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="9dd34-107">I tipi di token seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="9dd34-107">The following token types are valid:</span></span>  
  
-   `mdModuleRef`<span data-ttu-id="9dd34-108">, se il tipo è definito nello stesso assembly in cui è definito il chiamante.</span><span class="sxs-lookup"><span data-stu-id="9dd34-108">, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   `mdAssemblyRef`<span data-ttu-id="9dd34-109">, se il tipo è definito in un assembly diverso da quello in cui è definito il chiamante.</span><span class="sxs-lookup"><span data-stu-id="9dd34-109">, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   `mdTypeRef`<span data-ttu-id="9dd34-110">, se il tipo è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="9dd34-110">, if the type is a nested type.</span></span>  
  
-   `mdModule`<span data-ttu-id="9dd34-111">, se il tipo è definito nello stesso modulo in cui è definito il chiamante.</span><span class="sxs-lookup"><span data-stu-id="9dd34-111">, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="9dd34-112">Null se il tipo è definito a livello globale.</span><span class="sxs-lookup"><span data-stu-id="9dd34-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="9dd34-113">[in] Il nome del tipo di destinazione in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="9dd34-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="9dd34-114">[out] Un puntatore al `mdTypeRef` token assegnato al tipo.</span><span class="sxs-lookup"><span data-stu-id="9dd34-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dd34-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dd34-115">Requirements</span></span>  
 <span data-ttu-id="9dd34-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dd34-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dd34-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9dd34-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9dd34-118">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9dd34-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9dd34-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9dd34-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9dd34-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dd34-120">See also</span></span>

- [<span data-ttu-id="9dd34-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9dd34-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9dd34-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9dd34-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
