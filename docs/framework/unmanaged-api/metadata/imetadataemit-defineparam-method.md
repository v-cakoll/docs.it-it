---
title: Metodo IMetaDataEmit::DefineParam
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4bf36edfad504f2858a45d5e34891042d8850bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="a2a55-102">Metodo IMetaDataEmit::DefineParam</span><span class="sxs-lookup"><span data-stu-id="a2a55-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="a2a55-103">Crea una definizione di parametro con la firma specificata per il metodo a cui fa riferimento il token specificato e ottiene un token per la definizione di parametro.</span><span class="sxs-lookup"><span data-stu-id="a2a55-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2a55-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2a55-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2a55-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a2a55-106">[in] Il token per il metodo viene definito il cui parametro.</span><span class="sxs-lookup"><span data-stu-id="a2a55-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="a2a55-107">[in] Il numero di sequenza del parametro.</span><span class="sxs-lookup"><span data-stu-id="a2a55-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="a2a55-108">[in] Il nome del parametro in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="a2a55-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="a2a55-109">[in] Flag per il parametro.</span><span class="sxs-lookup"><span data-stu-id="a2a55-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="a2a55-110">Si tratta di una maschera di bit di `CorParamAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="a2a55-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="a2a55-111">[in] `ELEMENT_TYPE_`  *\**  per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="a2a55-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a2a55-112">[in] Il valore costante per il parametro.</span><span class="sxs-lookup"><span data-stu-id="a2a55-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="a2a55-113">[in] Le dimensioni, in caratteri Unicode, di `pValue`.</span><span class="sxs-lookup"><span data-stu-id="a2a55-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="a2a55-114">[out] Il `mdParamDef` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="a2a55-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2a55-115">Note</span><span class="sxs-lookup"><span data-stu-id="a2a55-115">Remarks</span></span>  
 <span data-ttu-id="a2a55-116">La sequenza di valori `ulParamSeq` iniziano con 1 per i parametri.</span><span class="sxs-lookup"><span data-stu-id="a2a55-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="a2a55-117">Valore restituito è un numero di sequenza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="a2a55-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2a55-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2a55-118">Requirements</span></span>  
 <span data-ttu-id="a2a55-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2a55-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2a55-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a2a55-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2a55-121">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2a55-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2a55-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2a55-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a55-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2a55-123">See Also</span></span>  
 [<span data-ttu-id="a2a55-124">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a2a55-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a2a55-125">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a2a55-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
