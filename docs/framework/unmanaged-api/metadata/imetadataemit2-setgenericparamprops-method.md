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
ms.openlocfilehash: fd7f149e806727d849cdceb3ffbc5dc7392fcf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177414"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="78552-102">Metodo IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="78552-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="78552-103">Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="78552-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78552-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78552-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78552-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78552-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="78552-106">[in] Token per la definizione di parametro generico per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="78552-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="78552-107">[in] Valore dell'enumerazione [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) che descrive il tipo per il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="78552-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="78552-108">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="78552-108">[in] Optional.</span></span> <span data-ttu-id="78552-109">Nome del parametro per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="78552-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="78552-110">[in] Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="78552-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="78552-111">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="78552-111">[in] Optional.</span></span> <span data-ttu-id="78552-112">Matrice con terminazione zero di vincoli di tipo.</span><span class="sxs-lookup"><span data-stu-id="78552-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="78552-113">I membri della `mdTypeDef` `mdTypeRef`matrice `mdTypeSpec` devono essere un token , o di metadati.</span><span class="sxs-lookup"><span data-stu-id="78552-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78552-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78552-114">Requirements</span></span>  
 <span data-ttu-id="78552-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78552-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78552-116">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="78552-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78552-117">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78552-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78552-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78552-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78552-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78552-119">See also</span></span>

- [<span data-ttu-id="78552-120">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="78552-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="78552-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="78552-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
