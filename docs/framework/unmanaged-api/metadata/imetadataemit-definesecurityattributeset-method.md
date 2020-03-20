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
ms.openlocfilehash: fadd1974cd4fa8a51a06700835f46df24e37d7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175772"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="07fc3-102">Metodo IMetaDataEmit::DefineSecurityAttributeSet</span><span class="sxs-lookup"><span data-stu-id="07fc3-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="07fc3-103">Crea un set di autorizzazioni di sicurezza da collegare all'oggetto a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="07fc3-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07fc3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07fc3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07fc3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="07fc3-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="07fc3-106">[in] Token a cui sono associate le informazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="07fc3-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="07fc3-107">[in] Matrice di `COR_SECATTR` strutture.</span><span class="sxs-lookup"><span data-stu-id="07fc3-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="07fc3-108">[in] Il numero di `rSecAttrs`elementi in .</span><span class="sxs-lookup"><span data-stu-id="07fc3-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="07fc3-109">[fuori] Se il metodo ha esito `rSecAttrs` negativo, specifica l'indice dell'elemento che ha causato il problema.</span><span class="sxs-lookup"><span data-stu-id="07fc3-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07fc3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07fc3-110">Requirements</span></span>  
 <span data-ttu-id="07fc3-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07fc3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07fc3-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07fc3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07fc3-113">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07fc3-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07fc3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07fc3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07fc3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07fc3-115">See also</span></span>

- [<span data-ttu-id="07fc3-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="07fc3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="07fc3-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="07fc3-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
