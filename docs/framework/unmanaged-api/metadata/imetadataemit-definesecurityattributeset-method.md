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
ms.openlocfilehash: 3f244d256d3af104d1d0c65769e82a87d6de046e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189014"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="fd580-102">Metodo IMetaDataEmit::DefineSecurityAttributeSet</span><span class="sxs-lookup"><span data-stu-id="fd580-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="fd580-103">Crea un set di autorizzazioni di sicurezza da associare all'oggetto a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="fd580-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd580-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd580-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd580-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd580-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="fd580-106">[in] Il token a cui sono collegate le informazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fd580-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="fd580-107">[in] Matrice di `COR_SECATTR` strutture.</span><span class="sxs-lookup"><span data-stu-id="fd580-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="fd580-108">[in] Il numero di elementi in `rSecAttrs`.</span><span class="sxs-lookup"><span data-stu-id="fd580-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="fd580-109">[out] Se il metodo ha esito negativo, specifica l'indice in `rSecAttrs` dell'elemento che ha causato il problema.</span><span class="sxs-lookup"><span data-stu-id="fd580-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd580-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd580-110">Requirements</span></span>  
 <span data-ttu-id="fd580-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd580-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd580-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fd580-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd580-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fd580-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fd580-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fd580-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fd580-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd580-115">See also</span></span>

- [<span data-ttu-id="fd580-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fd580-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fd580-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fd580-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
