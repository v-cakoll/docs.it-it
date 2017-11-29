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
ms.openlocfilehash: d78b6b3867cb168e4ebf93c07f17a911e1955832
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ceesectionreloctype-enumeration"></a>Enumerazione CeeSectionRelocType
Fornisce i valori che influenzano il tipo di `reloc` istruzione generato in una chiamata a [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`srRelocAbsolute`|Genera solo un relativo alla sezione `reloc`, inviando alcuna informazione in una sezione. reloc.|  
|`srRelocHighLow`|Genera un `reloc` per un percorso della dimensione del puntatore. Questo viene trasformato in BASED_HIGHLOW o BASED_DIR64 a seconda della piattaforma.|  
|`srRelocHighAdj`|Genera un `reloc` per i primi 16 bit di un numero a 32 bit, in cui sono inclusi i 16 bit nella parte inferiore della parola successiva nella tabella. reloc.|  
|`srRelocMapToken`|Genera una rilocazione della mappa del token, inviare alcuna informazione in una sezione. reloc.|  
|`srRelocRelative`|Indica che il valore è un'indirizzo relativo di correzione.|  
|`srRelocFilePos`|Genera solo un relativo alla sezione `reloc`, inviando alcuna informazione in una sezione. reloc. Questo `reloc` è relativo la posizione del file della sezione, non l'indirizzo virtuale.|  
|`srRelocCodeRelative`|Specifica un'indirizzo relativo al codice di correzione.|  
|`srRelocIA64Imm64`|Genera un `reloc` per un indirizzo a 64 bit in un ambiente ia64 `movl` istruzione.|  
|`srRelocDir64`|Genera un `reloc` per un indirizzo a 64 bit.|  
|`srRelocIA64PcRel25`|Generare un `reloc` per un indirizzo relativo al PC di 25 bit in un ambiente ia64 `br.call` istruzione.|  
|`srRelocIA64PcRel64`|Genera un `reloc` per un indirizzo relativo al PC a 64 bit in un ambiente ia64 `brl.call` istruzione.|  
|`srRelocAbsoluteTagged`|Genera un 30 bit relativo alla sezione `reloc`, utilizzato per i valori di puntatore con tag.|  
|`srRelocSentinel`|Un valore di sentinel per garantire le aggiunte a questa enumerazione viene riflesso nella interno `reloc` matrice nome.|  
|`srNoBaseReloc`|Specifica di non creare una base `reloc`.|  
|`srRelocPtr`|Un valore che indica che il contenuto di pre-correzione della memoria è un puntatore anziché una sezione di offset.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [ICeeGen (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [AddSectionReloc (metodo)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
