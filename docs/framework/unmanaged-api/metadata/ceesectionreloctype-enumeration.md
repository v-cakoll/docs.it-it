---
title: Enumerazione CeeSectionRelocType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocType
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocType
helpviewer_keywords: CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d257778a9a05e2654d7f91c0205424d001f5ae3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="a7303-102">Enumerazione CeeSectionRelocType</span><span class="sxs-lookup"><span data-stu-id="a7303-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="a7303-103">Fornisce i valori che influenzano il tipo di `reloc` istruzione generato in una chiamata a [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="a7303-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7303-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7303-104">Syntax</span></span>  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a><span data-ttu-id="a7303-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a7303-105">Members</span></span>  
  
|<span data-ttu-id="a7303-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a7303-106">Member</span></span>|<span data-ttu-id="a7303-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7303-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="a7303-108">Genera solo un relativo alla sezione `reloc`, inviando alcuna informazione in una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="a7303-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="a7303-109">Genera un `reloc` per un percorso della dimensione del puntatore.</span><span class="sxs-lookup"><span data-stu-id="a7303-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="a7303-110">Questo viene trasformato in BASED_HIGHLOW o BASED_DIR64 a seconda della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="a7303-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="a7303-111">Genera un `reloc` per i primi 16 bit di un numero a 32 bit, in cui sono inclusi i 16 bit nella parte inferiore della parola successiva nella tabella. reloc.</span><span class="sxs-lookup"><span data-stu-id="a7303-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="a7303-112">Genera una rilocazione della mappa del token, inviare alcuna informazione in una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="a7303-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="a7303-113">Indica che il valore è un'indirizzo relativo di correzione.</span><span class="sxs-lookup"><span data-stu-id="a7303-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="a7303-114">Genera solo un relativo alla sezione `reloc`, inviando alcuna informazione in una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="a7303-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="a7303-115">Questo `reloc` è relativo la posizione del file della sezione, non l'indirizzo virtuale.</span><span class="sxs-lookup"><span data-stu-id="a7303-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="a7303-116">Specifica un'indirizzo relativo al codice di correzione.</span><span class="sxs-lookup"><span data-stu-id="a7303-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="a7303-117">Genera un `reloc` per un indirizzo a 64 bit in un ambiente ia64 `movl` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a7303-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="a7303-118">Genera un `reloc` per un indirizzo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="a7303-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="a7303-119">Generare un `reloc` per un indirizzo relativo al PC di 25 bit in un ambiente ia64 `br.call` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a7303-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="a7303-120">Genera un `reloc` per un indirizzo relativo al PC a 64 bit in un ambiente ia64 `brl.call` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a7303-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="a7303-121">Genera un 30 bit relativo alla sezione `reloc`, utilizzato per i valori di puntatore con tag.</span><span class="sxs-lookup"><span data-stu-id="a7303-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="a7303-122">Un valore di sentinel per garantire le aggiunte a questa enumerazione viene riflesso nella interno `reloc` matrice nome.</span><span class="sxs-lookup"><span data-stu-id="a7303-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="a7303-123">Specifica di non creare una base `reloc`.</span><span class="sxs-lookup"><span data-stu-id="a7303-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="a7303-124">Un valore che indica che il contenuto di pre-correzione della memoria è un puntatore anziché una sezione di offset.</span><span class="sxs-lookup"><span data-stu-id="a7303-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7303-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7303-125">Requirements</span></span>  
 <span data-ttu-id="a7303-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7303-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7303-127">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a7303-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7303-128">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7303-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7303-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7303-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7303-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7303-130">See Also</span></span>  
 [<span data-ttu-id="a7303-131">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="a7303-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="a7303-132">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="a7303-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [<span data-ttu-id="a7303-133">Metodo AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="a7303-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
