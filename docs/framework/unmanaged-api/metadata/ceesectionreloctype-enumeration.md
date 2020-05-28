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
# <a name="ceesectionreloctype-enumeration"></a>Enumerazione CeeSectionRelocType
Fornisce valori per influenzare il tipo di `reloc` istruzione emessa in una chiamata a [ICeeGen:: AddSectionReloc](iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`srRelocAbsolute`|Genera solo una sezione relativa `reloc` , non inviando nulla a una sezione. reloc.|  
|`srRelocHighLow`|Genera un oggetto `reloc` per una posizione delle dimensioni del puntatore. Questa operazione viene trasformata in BASED_HIGHLOW o BASED_DIR64 a seconda della piattaforma.|  
|`srRelocHighAdj`|Genera un oggetto `reloc` per i primi 16 bit di un numero a 32 bit, dove i 16 bit inferiori sono inclusi nella parola successiva nella tabella. reloc.|  
|`srRelocMapToken`|Genera una rilocazione della mappa dei token, non inviando nulla a una sezione. reloc.|  
|`srRelocRelative`|Indica che il valore è una correzione di indirizzo relativa.|  
|`srRelocFilePos`|Genera solo una sezione relativa `reloc` , non inviando nulla a una sezione. reloc. Questo `reloc` è relativo alla posizione del file della sezione, non all'indirizzo virtuale della sezione.|  
|`srRelocCodeRelative`|Specifica una correzione di indirizzo relativa al codice.|  
|`srRelocIA64Imm64`|Genera un oggetto `reloc` per un indirizzo di bit 64 in un' `movl` istruzione ia64.|  
|`srRelocDir64`|Genera un oggetto `reloc` per un indirizzo a 64 bit.|  
|`srRelocIA64PcRel25`|Generare un oggetto `reloc` per un indirizzo relativo al PC a 25 bit in un' `br.call` istruzione ia64.|  
|`srRelocIA64PcRel64`|Genera un oggetto `reloc` per un indirizzo relativo al PC a 64 bit in un' `brl.call` istruzione ia64.|  
|`srRelocAbsoluteTagged`|Genera una sezione relativa a 30 bit `reloc` , utilizzata per i valori di puntatore con tag.|  
|`srRelocSentinel`|Valore sentinella che consente di garantire che eventuali aggiunte a questa enumerazione vengano riflesse nella `reloc` matrice di nomi interna.|  
|`srNoBaseReloc`|Specifica di non creare una base `reloc` .|  
|`srRelocPtr`|Valore che indica che il contenuto della pre-correzione della memoria è un puntatore anziché un offset di sezione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
- [Interfaccia ICeeGen](iceegen-interface.md)
- [Metodo AddSectionReloc](iceegen-addsectionreloc-method.md)
