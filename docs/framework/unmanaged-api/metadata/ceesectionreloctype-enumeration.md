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
ms.openlocfilehash: 78b30f624bd71234e8f1b56600b3a23d15fdf517
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006031"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="23f88-102">Enumerazione CeeSectionRelocType</span><span class="sxs-lookup"><span data-stu-id="23f88-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="23f88-103">Fornisce valori per influenzare il tipo di `reloc` istruzione emessa in una chiamata a [ICeeGen:: AddSectionReloc](iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="23f88-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23f88-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="23f88-105">Membri</span><span class="sxs-lookup"><span data-stu-id="23f88-105">Members</span></span>  
  
|<span data-ttu-id="23f88-106">Membro</span><span class="sxs-lookup"><span data-stu-id="23f88-106">Member</span></span>|<span data-ttu-id="23f88-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23f88-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="23f88-108">Genera solo una sezione relativa `reloc` , non inviando nulla a una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="23f88-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="23f88-109">Genera un oggetto `reloc` per una posizione delle dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="23f88-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="23f88-110">Questa operazione viene trasformata in BASED_HIGHLOW o BASED_DIR64 a seconda della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="23f88-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="23f88-111">Genera un oggetto `reloc` per i primi 16 bit di un numero a 32 bit, dove i 16 bit inferiori sono inclusi nella parola successiva nella tabella. reloc.</span><span class="sxs-lookup"><span data-stu-id="23f88-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="23f88-112">Genera una rilocazione della mappa dei token, non inviando nulla a una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="23f88-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="23f88-113">Indica che il valore è una correzione di indirizzo relativa.</span><span class="sxs-lookup"><span data-stu-id="23f88-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="23f88-114">Genera solo una sezione relativa `reloc` , non inviando nulla a una sezione. reloc.</span><span class="sxs-lookup"><span data-stu-id="23f88-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="23f88-115">Questo `reloc` è relativo alla posizione del file della sezione, non all'indirizzo virtuale della sezione.</span><span class="sxs-lookup"><span data-stu-id="23f88-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="23f88-116">Specifica una correzione di indirizzo relativa al codice.</span><span class="sxs-lookup"><span data-stu-id="23f88-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="23f88-117">Genera un oggetto `reloc` per un indirizzo di bit 64 in un' `movl` istruzione ia64.</span><span class="sxs-lookup"><span data-stu-id="23f88-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="23f88-118">Genera un oggetto `reloc` per un indirizzo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="23f88-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="23f88-119">Generare un oggetto `reloc` per un indirizzo relativo al PC a 25 bit in un' `br.call` istruzione ia64.</span><span class="sxs-lookup"><span data-stu-id="23f88-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="23f88-120">Genera un oggetto `reloc` per un indirizzo relativo al PC a 64 bit in un' `brl.call` istruzione ia64.</span><span class="sxs-lookup"><span data-stu-id="23f88-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="23f88-121">Genera una sezione relativa a 30 bit `reloc` , utilizzata per i valori di puntatore con tag.</span><span class="sxs-lookup"><span data-stu-id="23f88-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="23f88-122">Valore sentinella che consente di garantire che eventuali aggiunte a questa enumerazione vengano riflesse nella `reloc` matrice di nomi interna.</span><span class="sxs-lookup"><span data-stu-id="23f88-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="23f88-123">Specifica di non creare una base `reloc` .</span><span class="sxs-lookup"><span data-stu-id="23f88-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="23f88-124">Valore che indica che il contenuto della pre-correzione della memoria è un puntatore anziché un offset di sezione.</span><span class="sxs-lookup"><span data-stu-id="23f88-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23f88-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23f88-125">Requirements</span></span>  
 <span data-ttu-id="23f88-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23f88-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f88-127">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="23f88-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23f88-128">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="23f88-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23f88-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f88-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f88-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23f88-130">See also</span></span>

- [<span data-ttu-id="23f88-131">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="23f88-131">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="23f88-132">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="23f88-132">ICeeGen Interface</span></span>](iceegen-interface.md)
- [<span data-ttu-id="23f88-133">Metodo AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="23f88-133">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)
