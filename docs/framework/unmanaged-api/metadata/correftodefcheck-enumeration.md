---
title: Enumerazione CorRefToDefCheck
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e6c3c9b842bd823e8975661964480fd801779b2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450125"
---
# <a name="correftodefcheck-enumeration"></a>Enumerazione CorRefToDefCheck
Specifica i flag per controllare quali elementi a cui viene fatto riferimento vengono convertiti nelle relative definizioni per ottimizzare il codice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDRefToDefDefault`|Specifica che i riferimenti ai tipi e i riferimenti ai membri devono essere convertiti in definizioni. Si tratta del valore predefinito (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).|  
|`MDRefToDefAll`|Specifica che tutti gli elementi a cui si fa riferimento devono essere convertiti in definizioni.|  
|`MDRefToDefNone`|Specifica che nessun elemento a cui si fa riferimento deve essere convertito nelle definizioni.|  
|`MDTypeRefToDef`|Specifica che solo i riferimenti ai tipi devono essere convertiti nelle definizioni di tipo.|  
|`MDMemberRefToDef`|Specifica che solo i riferimenti ai membri devono essere convertiti in definizioni. Ovvero i riferimenti ai membri devono essere convertiti in definizioni di metodo o definizioni di campo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
