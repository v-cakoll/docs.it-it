---
title: Metodo IMetaDataEmit::DefineSecurityAttributeSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43009a81298fa5414df94e0664306859f0c9b851
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478740"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="e9454-102">Metodo IMetaDataEmit::DefineSecurityAttributeSet</span><span class="sxs-lookup"><span data-stu-id="e9454-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="e9454-103">Crea un set di autorizzazioni di sicurezza da associare all'oggetto a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="e9454-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9454-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9454-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9454-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9454-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="e9454-106">[in] Il token a cui sono collegate le informazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e9454-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="e9454-107">[in] Matrice di `COR_SECATTR` strutture.</span><span class="sxs-lookup"><span data-stu-id="e9454-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="e9454-108">[in] Il numero di elementi in `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="e9454-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="e9454-109">[out] Se il metodo ha esito negativo, specifica l'indice in `rSecAttrs` dell'elemento che ha causato il problema.</span><span class="sxs-lookup"><span data-stu-id="e9454-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9454-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9454-110">Requirements</span></span>  
 <span data-ttu-id="e9454-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9454-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9454-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9454-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9454-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e9454-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9454-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9454-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9454-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9454-115">See also</span></span>
- [<span data-ttu-id="e9454-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e9454-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e9454-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e9454-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
