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
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176214"
---
# <a name="ceesectionreloctype-enumeration"></a>Enumerazione CeeSectionRelocType
Fornisce valori per influenzare il tipo di `reloc` istruzione emessa in una chiamata a [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
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
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`srRelocAbsolute`|Genera solo una `reloc`sezione relativa , non inviando nulla in una sezione .reloc.|  
|`srRelocHighLow`|Genera `reloc` un per una posizione delle dimensioni del puntatore. Questo si trasforma in BASED_HIGHLOW o BASED_DIR64 a seconda della piattaforma.|  
|`srRelocHighAdj`|Genera `reloc` un per i primi 16 bit di un numero a 32 bit, in cui i 16 bit inferiori sono inclusi nella parola successiva nella tabella .reloc.|  
|`srRelocMapToken`|Genera una rilocazione della mappa di token, non inviando nulla in una sezione .reloc.|  
|`srRelocRelative`|Indica che il valore è una correzione dell'indirizzo relativo.|  
|`srRelocFilePos`|Genera solo una `reloc`sezione relativa , non inviando nulla in una sezione .reloc. Questo `reloc` è relativo alla posizione del file della sezione, non l'indirizzo virtuale della sezione.|  
|`srRelocCodeRelative`|Specifica una correzione dell'indirizzo relativo al codice.|  
|`srRelocIA64Imm64`|Genera `reloc` un per un indirizzo a 64 `movl` bit in un'istruzione ia64.|  
|`srRelocDir64`|Genera `reloc` un per un indirizzo a 64 bit.|  
|`srRelocIA64PcRel25`|Generare `reloc` un per un indirizzo relativo al PC `br.call` a 25 bit in un'istruzione ia64.|  
|`srRelocIA64PcRel64`|Genera `reloc` un per un indirizzo relativo al PC a `brl.call` 64 bit in un'istruzione ia64.|  
|`srRelocAbsoluteTagged`|Genera un oggetto relativo `reloc`alla sezione a 30 bit , utilizzato per i valori dei puntatori con tag.|  
|`srRelocSentinel`|Un valore sentinel per garantire che eventuali aggiunte a `reloc` questa enumerazione vengano riflesse nella matrice di nomi interni.|  
|`srNoBaseReloc`|Specifica di non generare un file base `reloc`.|  
|`srRelocPtr`|Valore che indica che il contenuto di pre-correzione della memoria è un puntatore anziché un offset di sezione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [Interfaccia ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [Metodo AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
