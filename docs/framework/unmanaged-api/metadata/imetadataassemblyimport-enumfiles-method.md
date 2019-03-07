---
title: Metodo IMetaDataAssemblyImport::EnumFiles
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5848a14a20b63ffbf806bb56886b75360323b698
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496183"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="73206-102">Metodo IMetaDataAssemblyImport::EnumFiles</span><span class="sxs-lookup"><span data-stu-id="73206-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="73206-103">Enumera i file di cui viene fatto riferimento nel manifesto dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="73206-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73206-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73206-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73206-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73206-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="73206-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="73206-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="73206-107">Deve trattarsi di un valore null per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="73206-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="73206-108">[out] La matrice utilizzata per archiviare il `mdFile` i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="73206-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="73206-109">[in] Il numero massimo di `mdFile` i token che possono essere inseriti in `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="73206-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="73206-110">[out] I numerosi `mdFile` token effettivamente posizionati nella `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="73206-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73206-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="73206-111">Return Value</span></span>  
  
|<span data-ttu-id="73206-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73206-112">HRESULT</span></span>|<span data-ttu-id="73206-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73206-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="73206-114">`EnumFiles` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="73206-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="73206-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="73206-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="73206-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="73206-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73206-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73206-117">Requirements</span></span>  
 <span data-ttu-id="73206-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73206-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73206-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="73206-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73206-120">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="73206-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73206-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73206-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73206-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73206-122">See also</span></span>
- [<span data-ttu-id="73206-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="73206-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
