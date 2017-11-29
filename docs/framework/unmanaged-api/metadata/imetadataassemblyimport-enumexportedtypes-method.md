---
title: Metodo IMetaDataAssemblyImport::EnumExportedTypes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumExportedTypes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76c73cc3d13089b4a38a47d523d8baa77f6eed12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="7cbe1-102">Metodo IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="7cbe1-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="7cbe1-103">Enumera i tipi esportati a cui fa riferimento nel manifesto dell'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cbe1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cbe1-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cbe1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7cbe1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7cbe1-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7cbe1-107">Deve essere un valore null valore quando il `EnumExportedTypes` metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="7cbe1-108">[out] L'enumerazione di `mdExportedType` i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7cbe1-109">[in] Il numero massimo di `mdExportedType` i token che possono essere inseriti nel `rExportedTypes` matrice.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7cbe1-110">[out] Il numero di `mdExportedType` token effettivamente inseriti in `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cbe1-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7cbe1-111">Return Value</span></span>  
  
|<span data-ttu-id="7cbe1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cbe1-112">HRESULT</span></span>|<span data-ttu-id="7cbe1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cbe1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7cbe1-114">`EnumExportedTypes`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7cbe1-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7cbe1-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="7cbe1-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7cbe1-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7cbe1-117">Requirements</span></span>  
 <span data-ttu-id="7cbe1-118">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cbe1-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cbe1-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7cbe1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cbe1-120">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cbe1-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cbe1-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cbe1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cbe1-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cbe1-122">See Also</span></span>  
 [<span data-ttu-id="7cbe1-123">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7cbe1-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
