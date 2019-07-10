---
title: Enumerazione CorValidatorModuleType
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04bed418d96658e29328cf2ce6bba445639b437f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750753"
---
# <a name="corvalidatormoduletype-enumeration"></a>Enumerazione CorValidatorModuleType
Specifica il tipo di un modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|Il modulo è un tipo non valido.|  
|`ValidatorModuleTypeMin`|Il valore minimo del `CorValidatorModuleType` enum.|  
|`ValidatorModuleTypePE`|Il modulo è un file eseguibile portabile (PE).|  
|`ValidatorModuleTypeObj`|Il modulo è un file con estensione obj.|  
|`ValidatorModuleTypeEnc`|Il modulo è una sessione di modifica e continuazione del debugger.|  
|`ValidatorModuleTypeIncr`|Il modulo è quello che è stata compilata in modo incrementale.|  
|`ValidatorModuleTypeMax`|Il valore massimo del `CorValidatorModuleType` enum.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
