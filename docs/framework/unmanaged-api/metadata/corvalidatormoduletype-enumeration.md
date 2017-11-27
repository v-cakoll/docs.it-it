---
title: Enumerazione CorValidatorModuleType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorValidatorModuleType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorValidatorModuleType
helpviewer_keywords: CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa7ca08398358dcf00a986c356de365e9caafc4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corvalidatormoduletype-enumeration"></a>Enumerazione CorValidatorModuleType
Specifica il tipo di un modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|Il modulo è un tipo non valido.|  
|`ValidatorModuleTypeMin`|Il valore minimo di `CorValidatorModuleType` enum.|  
|`ValidatorModuleTypePE`|Il modulo è un file eseguibile portabile (PE).|  
|`ValidatorModuleTypeObj`|Il modulo è un file con estensione obj.|  
|`ValidatorModuleTypeEnc`|Il modulo è una sessione di modifica e continuazione del debugger.|  
|`ValidatorModuleTypeIncr`|Il modulo è quello che è stata compilata in modo incrementale.|  
|`ValidatorModuleTypeMax`|Il valore massimo di `CorValidatorModuleType` enum.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
