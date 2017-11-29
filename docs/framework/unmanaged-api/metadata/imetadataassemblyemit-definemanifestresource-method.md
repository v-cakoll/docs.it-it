---
title: Metodo IMetaDataAssemblyEmit::DefineManifestResource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="ac0d4-102">Metodo IMetaDataAssemblyEmit::DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="ac0d4-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="ac0d4-103">Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac0d4-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac0d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac0d4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ac0d4-106">[in] Il nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="ac0d4-107">[in] Un token di metadati del tipo `mdtFile` o `mdtAssemblyRef` che esegue il mapping al provider di risorse.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="ac0d4-108">Un valore NULL indica che il file in cui sono incorporato i metadati sia il provider di risorse.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="ac0d4-109">[in] L'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="ac0d4-110">Per le risorse nei file autonomi, questo valore sarà sempre zero.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="ac0d4-111">Se la risorsa è incorporata in un file di PE (eseguibile), si tratta di un offset del BLOB, che inizia nella posizione specificata nel file di intestazione Cor. h della risorsa.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="ac0d4-112">[in] Combinazione bit per bit dei valori di flag che specificano le impostazioni delle proprietà per la definizione di risorsa.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="ac0d4-113">[out] Un puntatore al token di metadati restituiti.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac0d4-114">Note</span><span class="sxs-lookup"><span data-stu-id="ac0d4-114">Remarks</span></span>  
 <span data-ttu-id="ac0d4-115">Una `ManifestResource` struttura dei metadati deve essere definita per ogni risorsa è implementata in ognuno dei file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ac0d4-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0d4-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac0d4-116">Requirements</span></span>  
 <span data-ttu-id="ac0d4-117">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac0d4-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac0d4-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ac0d4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac0d4-119">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac0d4-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac0d4-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac0d4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0d4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac0d4-121">See Also</span></span>  
 [<span data-ttu-id="ac0d4-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="ac0d4-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
