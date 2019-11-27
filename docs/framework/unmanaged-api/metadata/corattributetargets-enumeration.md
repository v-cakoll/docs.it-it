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
ms.openlocfilehash: 5f83cb96e39b257a1d35786130cd5ed31d071de7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443877"
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
|`catAssembly`|L'attributo può essere applicato a un assembly.|  
|`catModule`|L'attributo può essere applicato a un modulo eseguibile (con estensione dll o exe) portatile.|  
|`catClass`|L'attributo può essere applicato a una classe.|  
|`catStruct`|L'attributo può essere applicato a una struttura; ovvero un tipo di valore.|  
|`catEnum`|L'attributo può essere applicato a un'enumerazione.|  
|`catConstructor`|L'attributo può essere applicato a un costruttore.|  
|`catMethod`|L'attributo può essere applicato a un metodo.|  
|`catProperty`|L'attributo può essere applicato a una proprietà.|  
|`catField`|L'attributo può essere applicato a un campo.|  
|`catEvent`|L'attributo può essere applicato a un evento.|  
|`catInterface`|L'attributo può essere applicato a un'interfaccia.|  
|`catParameter`|L'attributo può essere applicato a un parametro.|  
|`catDelegate`|L'attributo può essere applicato a un delegato.|  
|`catGenericParameter`|L'attributo può essere applicato a un parametro generico.|  
|`catAll`|L'attributo può essere applicato a qualsiasi elemento dell'applicazione.|  
|`catClassMembers`|L'attributo può essere applicato a un membro di una classe.|  
  
## <a name="remarks"></a>Note  
 I valori di enumerazione `CorAttributeTargets` possono essere combinati con un'operazione OR bit per bit per ottenere la combinazione preferita.  
  
 Il `CorAttributeTargets` in parallelo all'enumerazione <xref:System.AttributeTargets?displayProperty=nameWithType> gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
