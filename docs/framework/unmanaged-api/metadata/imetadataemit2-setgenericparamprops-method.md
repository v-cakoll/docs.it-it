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
ms.openlocfilehash: 8feba8e67f3a90dd48fd957065a9c166c204b87c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492733"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="2ffba-102">Metodo IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="2ffba-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="2ffba-103">Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="2ffba-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ffba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ffba-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ffba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ffba-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="2ffba-106">in Token per la definizione del parametro generico per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="2ffba-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2ffba-107">in Valore dell'enumerazione [CorGenericParamAttr](corgenericparamattr-enumeration.md) che descrive il tipo per il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="2ffba-107">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="2ffba-108">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2ffba-108">[in] Optional.</span></span> <span data-ttu-id="2ffba-109">Nome del parametro per il quale impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="2ffba-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="2ffba-110">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="2ffba-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="2ffba-111">[in] Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2ffba-111">[in] Optional.</span></span> <span data-ttu-id="2ffba-112">Matrice con terminazione zero di vincoli di tipo.</span><span class="sxs-lookup"><span data-stu-id="2ffba-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="2ffba-113">I membri della matrice devono essere un `mdTypeDef` `mdTypeRef` token di metadati, o `mdTypeSpec` .</span><span class="sxs-lookup"><span data-stu-id="2ffba-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ffba-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ffba-114">Requirements</span></span>  
 <span data-ttu-id="2ffba-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ffba-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ffba-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2ffba-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ffba-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ffba-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ffba-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ffba-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ffba-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ffba-119">See also</span></span>

- [<span data-ttu-id="2ffba-120">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2ffba-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="2ffba-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2ffba-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
