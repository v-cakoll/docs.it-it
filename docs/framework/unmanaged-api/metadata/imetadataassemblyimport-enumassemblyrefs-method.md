---
title: Metodo IMetaDataAssemblyImport::EnumAssemblyRefs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 6a4489d094974eb872b39824ceb185b0cbe48625
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177823"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="a3a60-102">Metodo IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="a3a60-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="a3a60-103">Enumera le `mdAssemblyRef` istanze definite nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3a60-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3a60-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3a60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3a60-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a3a60-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a3a60-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a3a60-107">Deve essere un valore `EnumAssemblyRefs` null quando il metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="a3a60-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="a3a60-108">[fuori] Enumerazione `mdAssemblyRef` dei token di metadati.</span><span class="sxs-lookup"><span data-stu-id="a3a60-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a3a60-109">[in] Numero massimo di token che possono `rAssemblyRefs` essere inseriti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="a3a60-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a3a60-110">[fuori] Il numero di token `rAssemblyRefs`effettivamente inseriti in .</span><span class="sxs-lookup"><span data-stu-id="a3a60-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3a60-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a3a60-111">Return Value</span></span>  
  
|<span data-ttu-id="a3a60-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3a60-112">HRESULT</span></span>|<span data-ttu-id="a3a60-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3a60-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a3a60-114">`EnumAssemblyRefs`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="a3a60-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a3a60-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="a3a60-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a3a60-116">In questo `pcTokens` caso, è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="a3a60-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3a60-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3a60-117">Requirements</span></span>  
 <span data-ttu-id="a3a60-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3a60-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3a60-119">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a3a60-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3a60-120">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3a60-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3a60-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3a60-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a60-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3a60-122">See also</span></span>

- [<span data-ttu-id="a3a60-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="a3a60-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
