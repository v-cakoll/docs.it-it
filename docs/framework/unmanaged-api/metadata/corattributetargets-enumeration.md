---
title: Enumerazione CorAttributeTargets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAttributeTargets
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAttributeTargets
helpviewer_keywords: CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ce701c026b4e977c376b6e6f0f342b031634e38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corattributetargets-enumeration"></a>Enumerazione CorAttributeTargets
Specifica gli elementi dell'applicazione ai quali è valido applicare un attributo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`catAssembly`|Attributo può essere applicato a un assembly.|  
|`catModule`|Attributo può essere applicato a un modulo (con estensione dll o .exe) eseguibile portabile.|  
|`catClass`|Attributo può essere applicato a una classe.|  
|`catStruct`|Attributo può essere applicato a una struttura; ovvero, un tipo di valore.|  
|`catEnum`|Attributo può essere applicato a un'enumerazione.|  
|`catConstructor`|Attributo può essere applicato a un costruttore.|  
|`catMethod`|Attributo può essere applicato a un metodo.|  
|`catProperty`|Attributo può essere applicato a una proprietà.|  
|`catField`|Attributo può essere applicato a un campo.|  
|`catEvent`|Attributo può essere applicato a un evento.|  
|`catInterface`|Attributo può essere applicato a un'interfaccia.|  
|`catParameter`|Attributo può essere applicato a un parametro.|  
|`catDelegate`|Attributo può essere applicato a un delegato.|  
|`catGenericParameter`|Attributo può essere applicato a un parametro generico.|  
|`catAll`|Attributo può essere applicato a qualsiasi elemento dell'applicazione.|  
|`catClassMembers`|Attributo può essere applicato a un membro di una classe.|  
  
## <a name="remarks"></a>Note  
 Il `CorAttributeTargets` valori di enumerazione possono essere combinati con un'operazione OR bit per bit per ottenere la combinazione desiderata.  
  
 Il `CorAttributeTargets` parallelo gestito <xref:System.AttributeTargets?displayProperty=nameWithType> enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
