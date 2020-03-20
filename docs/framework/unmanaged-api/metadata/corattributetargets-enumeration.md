---
title: Enumerazione CorAttributeTargets
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: 51741aa3a6d965c1e9743081628d8ad62e8fb04e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176201"
---
# <a name="corattributetargets-enumeration"></a>Enumerazione CorAttributeTargets
Specifica gli elementi dell'applicazione ai quali è valido applicare un attributo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`catAssembly`|Attributo applicabile a un assembly.|  
|`catModule`|L'attributo può essere applicato a un modulo eseguibile portabile (con estensione dll o exe).|  
|`catClass`|Attributo applicabile a una classe.|  
|`catStruct`|Attributo applicabile a una struttura, ovvero a un tipo valore.|  
|`catEnum`|Attributo applicabile a un'enumerazione.|  
|`catConstructor`|Attributo applicabile a un costruttore.|  
|`catMethod`|Attributo applicabile a un metodo.|  
|`catProperty`|Attributo applicabile a una proprietà.|  
|`catField`|Attributo applicabile a un campo.|  
|`catEvent`|Attributo applicabile a un evento.|  
|`catInterface`|Attributo applicabile a un'interfaccia.|  
|`catParameter`|Attributo applicabile a un parametro.|  
|`catDelegate`|Attributo applicabile a un delegato.|  
|`catGenericParameter`|Attributo applicabile a un parametro generico.|  
|`catAll`|Attributo applicabile a tutti gli elementi dell'applicazione.|  
|`catClassMembers`|L'attributo può essere applicato a un membro di una classe.|  
  
## <a name="remarks"></a>Osservazioni  
 I `CorAttributeTargets` valori di enumerazione possono essere combinati con un'operazione OR bit per bit per ottenere la combinazione preferita.  
  
 L'enumerazione `CorAttributeTargets` <xref:System.AttributeTargets?displayProperty=nameWithType> gestita è parallela.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr.h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
