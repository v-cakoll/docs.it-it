---
title: Metodo IMetaDataEmit2::SetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d74ee7512f640ab906f1119f61e4998b5e882eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445687"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="cbfb7-102">Metodo IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="cbfb7-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="cbfb7-103">Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbfb7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbfb7-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbfb7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbfb7-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="cbfb7-106">[in] Il token per la definizione di parametro generico per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="cbfb7-107">[in] Il valore di [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumerazione che descrive il tipo per il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="cbfb7-108">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-108">[in] Optional.</span></span> <span data-ttu-id="cbfb7-109">Il nome del parametro per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="cbfb7-110">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="cbfb7-111">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-111">[in] Optional.</span></span> <span data-ttu-id="cbfb7-112">Una matrice con terminazione zero vincoli di tipo.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="cbfb7-113">Membri della matrice devono essere un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token di metadati.</span><span class="sxs-lookup"><span data-stu-id="cbfb7-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbfb7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbfb7-114">Requirements</span></span>  
 <span data-ttu-id="cbfb7-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbfb7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbfb7-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cbfb7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbfb7-117">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cbfb7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbfb7-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbfb7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfb7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbfb7-119">See Also</span></span>  
 [<span data-ttu-id="cbfb7-120">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cbfb7-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="cbfb7-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cbfb7-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
