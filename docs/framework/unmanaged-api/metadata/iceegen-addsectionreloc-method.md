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
ms.openlocfilehash: da3b83191ce1acdf40e27c5ee1d843a1fb4a54f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750685"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="7f16c-102">Metodo ICeeGen::AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="7f16c-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="7f16c-103">Aggiunge un'istruzione. reloc alla base di codice.</span><span class="sxs-lookup"><span data-stu-id="7f16c-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="7f16c-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7f16c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f16c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f16c-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f16c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f16c-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7f16c-107">[in] La sezione di codice in memoria a cui aggiungere un'istruzione. reloc.</span><span class="sxs-lookup"><span data-stu-id="7f16c-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="7f16c-108">[in] L'offset della sezione.</span><span class="sxs-lookup"><span data-stu-id="7f16c-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="7f16c-109">[in] La sezione in cui `offset` fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="7f16c-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="7f16c-110">[in] Uno dei [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) valori, che indica il tipo di istruzione. reloc da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="7f16c-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f16c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f16c-111">Requirements</span></span>  
 <span data-ttu-id="7f16c-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f16c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f16c-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7f16c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f16c-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7f16c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f16c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f16c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f16c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f16c-116">See also</span></span>

- [<span data-ttu-id="7f16c-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="7f16c-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
