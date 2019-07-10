---
title: Enumerazione CorParamAttr
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfa8f1b5df76c7fdfe2f25b637b157bfa4424f7a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781659"
---
# <a name="corparamattr-enumeration"></a>Enumerazione CorParamAttr
Contiene valori che descrivono i metadati di un parametro di metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`pdIn`|Specifica che il parametro viene passato nella chiamata al metodo.|  
|`pdOut`|Specifica che il parametro viene passato dal metodo restituito.|  
|`pdOptional`|Specifica che il parametro è facoltativo.|  
|`pdReservedMask`|Riservato per uso interno da common language runtime.|  
|`pdHasDefault`|Specifica che il parametro ha un valore predefinito.|  
|`pdHasFieldMarshal`|Specifica che il parametro contiene le informazioni di marshalling.|  
|`pdUnused`|Non usato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
