---
title: Enumerazione CeeSectionRelocType
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
ms.openlocfilehash: efce0c13944b383c42cbff6a6af4795293ee2989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444164"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="50e60-102">Enumerazione CeeSectionRelocType</span><span class="sxs-lookup"><span data-stu-id="50e60-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="50e60-103">Fornisce valori per influenzare il tipo di `reloc` istruzione emessa in una chiamata a [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="50e60-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50e60-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="50e60-105">Membri</span><span class="sxs-lookup"><span data-stu-id="50e60-105">Members</span></span>  
  
|<span data-ttu-id="50e60-106">Membro</span><span class="sxs-lookup"><span data-stu-id="50e60-106">Member</span></span>|<span data-ttu-id="50e60-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50e60-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="50e60-108">Genera solo una `reloc`relativa alla sezione, non inviando nulla a una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="50e60-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="50e60-109">Genera un `reloc` per una posizione con dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="50e60-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="50e60-110">Questa operazione viene trasformata in BASED_HIGHLOW o BASED_DIR64 a seconda della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="50e60-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="50e60-111">Genera un `reloc` per i primi 16 bit di un numero a 32 bit, dove i 16 bit inferiori sono inclusi nella parola successiva nella tabella. reloc.</span><span class="sxs-lookup"><span data-stu-id="50e60-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="50e60-112">Genera una rilocazione della mappa dei token, non inviando nulla a una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="50e60-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="50e60-113">Indica che il valore è una correzione di indirizzo relativa.</span><span class="sxs-lookup"><span data-stu-id="50e60-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="50e60-114">Genera solo una `reloc`relativa alla sezione, non inviando nulla a una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="50e60-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="50e60-115">Questo `reloc` è relativo alla posizione del file della sezione, non all'indirizzo virtuale della sezione.</span><span class="sxs-lookup"><span data-stu-id="50e60-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="50e60-116">Specifica una correzione di indirizzo relativa al codice.</span><span class="sxs-lookup"><span data-stu-id="50e60-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="50e60-117">Genera un `reloc` per un indirizzo a 64 bit in un'istruzione `movl` ia64.</span><span class="sxs-lookup"><span data-stu-id="50e60-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="50e60-118">Genera un `reloc` per un indirizzo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="50e60-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="50e60-119">Generare un `reloc` per un indirizzo relativo al PC a 25 bit in un'istruzione `br.call` ia64.</span><span class="sxs-lookup"><span data-stu-id="50e60-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="50e60-120">Genera un `reloc` per un indirizzo relativo al PC a 64 bit in un'istruzione `brl.call` ia64.</span><span class="sxs-lookup"><span data-stu-id="50e60-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="50e60-121">Genera una `reloc`relativa alla sezione a 30 bit, utilizzata per i valori di puntatore con tag.</span><span class="sxs-lookup"><span data-stu-id="50e60-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="50e60-122">Valore sentinella che consente di garantire che eventuali aggiunte a questa enumerazione vengano riflesse nella matrice di nomi di `reloc` interni.</span><span class="sxs-lookup"><span data-stu-id="50e60-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="50e60-123">Specifica di non generare un `reloc`di base.</span><span class="sxs-lookup"><span data-stu-id="50e60-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="50e60-124">Valore che indica che il contenuto della pre-correzione della memoria è un puntatore anziché un offset di sezione.</span><span class="sxs-lookup"><span data-stu-id="50e60-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50e60-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50e60-125">Requirements</span></span>  
 <span data-ttu-id="50e60-126">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50e60-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e60-127">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="50e60-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50e60-128">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50e60-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50e60-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e60-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e60-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50e60-130">See also</span></span>

- [<span data-ttu-id="50e60-131">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="50e60-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="50e60-132">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="50e60-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="50e60-133">Metodo AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="50e60-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
