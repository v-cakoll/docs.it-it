---
title: Metodo ICeeGen::AddSectionReloc
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c281d03c6e3774938cfa6e4b4b3a541738b38489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444343"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="447a8-102">Metodo ICeeGen::AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="447a8-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="447a8-103">Aggiunge un'istruzione. reloc alla base di codice.</span><span class="sxs-lookup"><span data-stu-id="447a8-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="447a8-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="447a8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="447a8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="447a8-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="447a8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="447a8-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="447a8-107">[in] La sezione di codice in memoria a cui aggiungere un'istruzione. reloc.</span><span class="sxs-lookup"><span data-stu-id="447a8-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="447a8-108">[in] L'offset della sezione.</span><span class="sxs-lookup"><span data-stu-id="447a8-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="447a8-109">[in] La sezione in cui `offset` fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="447a8-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="447a8-110">[in] Uno del [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) valori, che indica il tipo di istruzione. reloc da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="447a8-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="447a8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="447a8-111">Requirements</span></span>  
 <span data-ttu-id="447a8-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="447a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="447a8-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="447a8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="447a8-114">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="447a8-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="447a8-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="447a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447a8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="447a8-116">See Also</span></span>  
 [<span data-ttu-id="447a8-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="447a8-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
