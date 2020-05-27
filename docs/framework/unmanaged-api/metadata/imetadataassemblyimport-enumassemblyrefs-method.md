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
ms.openlocfilehash: 1b9700455da82fc7f4a39d4c208ac0b18ef79722
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009119"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="fe86c-102">Metodo IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="fe86c-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="fe86c-103">Enumera le `mdAssemblyRef` istanze definite nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fe86c-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe86c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe86c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe86c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe86c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fe86c-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="fe86c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fe86c-107">Deve essere un valore null quando il `EnumAssemblyRefs` metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="fe86c-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="fe86c-108">out Enumerazione dei `mdAssemblyRef` token di metadati.</span><span class="sxs-lookup"><span data-stu-id="fe86c-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fe86c-109">in Numero massimo di token che è possibile inserire nella `rAssemblyRefs` matrice.</span><span class="sxs-lookup"><span data-stu-id="fe86c-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fe86c-110">out Numero di token effettivamente inseriti in `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="fe86c-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe86c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe86c-111">Return Value</span></span>  
  
|<span data-ttu-id="fe86c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe86c-112">HRESULT</span></span>|<span data-ttu-id="fe86c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe86c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fe86c-114">`EnumAssemblyRefs`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="fe86c-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fe86c-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="fe86c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fe86c-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="fe86c-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe86c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe86c-117">Requirements</span></span>  
 <span data-ttu-id="fe86c-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe86c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe86c-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fe86c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe86c-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe86c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe86c-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe86c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe86c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe86c-122">See also</span></span>

- [<span data-ttu-id="fe86c-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="fe86c-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
