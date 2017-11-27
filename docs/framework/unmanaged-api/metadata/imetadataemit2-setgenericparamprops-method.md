---
title: Metodo IMetaDataEmit2::SetGenericParamProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5de54b3d113c8d43bd004b18e0a6cb22b1051dc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="8815e-102">Metodo IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="8815e-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="8815e-103">Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="8815e-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8815e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8815e-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8815e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8815e-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="8815e-106">[in] Il token per la definizione di parametro generico per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="8815e-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="8815e-107">[in] Il valore di [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumerazione che descrive il tipo per il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="8815e-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="8815e-108">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8815e-108">[in] Optional.</span></span> <span data-ttu-id="8815e-109">Il nome del parametro per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="8815e-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="8815e-110">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="8815e-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="8815e-111">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8815e-111">[in] Optional.</span></span> <span data-ttu-id="8815e-112">Una matrice con terminazione zero vincoli di tipo.</span><span class="sxs-lookup"><span data-stu-id="8815e-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="8815e-113">Membri della matrice devono essere un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token di metadati.</span><span class="sxs-lookup"><span data-stu-id="8815e-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8815e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8815e-114">Requirements</span></span>  
 <span data-ttu-id="8815e-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8815e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8815e-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8815e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8815e-117">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8815e-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8815e-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8815e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8815e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8815e-119">See Also</span></span>  
 [<span data-ttu-id="8815e-120">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8815e-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="8815e-121">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8815e-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
