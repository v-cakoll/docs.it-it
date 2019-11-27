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
# <a name="ceesectionreloctype-enumeration"></a>Enumerazione CeeSectionRelocType
Fornisce valori per influenzare il tipo di `reloc` istruzione emessa in una chiamata a [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
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
|`srRelocAbsolute`|Genera solo una `reloc`relativa alla sezione, non inviando nulla a una sezione. reloc.|  
|`srRelocHighLow`|Genera un `reloc` per una posizione con dimensioni del puntatore. Questa operazione viene trasformata in BASED_HIGHLOW o BASED_DIR64 a seconda della piattaforma.|  
|`srRelocHighAdj`|Genera un `reloc` per i primi 16 bit di un numero a 32 bit, dove i 16 bit inferiori sono inclusi nella parola successiva nella tabella. reloc.|  
|`srRelocMapToken`|Genera una rilocazione della mappa dei token, non inviando nulla a una sezione. reloc.|  
|`srRelocRelative`|Indica che il valore è una correzione di indirizzo relativa.|  
|`srRelocFilePos`|Genera solo una `reloc`relativa alla sezione, non inviando nulla a una sezione. reloc. Questo `reloc` è relativo alla posizione del file della sezione, non all'indirizzo virtuale della sezione.|  
|`srRelocCodeRelative`|Specifica una correzione di indirizzo relativa al codice.|  
|`srRelocIA64Imm64`|Genera un `reloc` per un indirizzo a 64 bit in un'istruzione `movl` ia64.|  
|`srRelocDir64`|Genera un `reloc` per un indirizzo a 64 bit.|  
|`srRelocIA64PcRel25`|Generare un `reloc` per un indirizzo relativo al PC a 25 bit in un'istruzione `br.call` ia64.|  
|`srRelocIA64PcRel64`|Genera un `reloc` per un indirizzo relativo al PC a 64 bit in un'istruzione `brl.call` ia64.|  
|`srRelocAbsoluteTagged`|Genera una `reloc`relativa alla sezione a 30 bit, utilizzata per i valori di puntatore con tag.|  
|`srRelocSentinel`|Valore sentinella che consente di garantire che eventuali aggiunte a questa enumerazione vengano riflesse nella matrice di nomi di `reloc` interni.|  
|`srNoBaseReloc`|Specifica di non generare un `reloc`di base.|  
|`srRelocPtr`|Valore che indica che il contenuto della pre-correzione della memoria è un puntatore anziché un offset di sezione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Interfaccia ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [Metodo AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
