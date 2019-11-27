---
title: Enumerazione CorSetENC
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: 39f72e670ddc700c257f50f6bad6fab702ec21b6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432769"
---
# <a name="corsetenc-enumeration"></a>Enumerazione CorSetENC
Contiene valori usati per influenzare il comportamento durante la generazione di metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|description|  
|------------|-----------------|  
|`MDSetENCOn`|Obsoleta.|  
|`MDSetENCOff`|Obsoleta.|  
|`MDUpdateENC`|Indica che, mentre i metadati possono essere aggiornati, i token non possono essere spostati.|  
|`MDUpdateFull`|Indica che i token possono essere spostati durante gli aggiornamenti.|  
|`MDUpdateExtension`|Indica che gli aggiornamenti possono essere costituiti solo da aggiunte. Non è possibile spostare i token.|  
|`MDUpdateIncremental`|Indica che la compilazione è incrementale.|  
|`MDUpdateDelta`|Indica che devono essere salvati solo i metadati modificati.|  
|`MDUpdateMask`|Include `MDUpdateENC`, `MDUpdateFull` e `MDUpdateIncremental`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
