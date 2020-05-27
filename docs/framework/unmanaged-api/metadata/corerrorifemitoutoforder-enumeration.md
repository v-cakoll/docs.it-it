---
title: Enumerazione CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: fec049297bfa12d86cb2a7f7950e84ae540832b1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007433"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>Enumerazione CorErrorIfEmitOutOfOrder
Contiene valori di flag che indicano in quali condizioni è necessario generare un messaggio di errore per notificare che i metadati sono stati emessi senza ordine.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Indica il comportamento predefinito, che non genera messaggi di errore.|  
|`MDErrorOutOfOrderNone`|Indica che il compilatore non deve generare messaggi di errore.|  
|`MDErrorOutOfOrderAll`|Indica che il compilatore deve generare un messaggio di errore quando un campo, una proprietà, un evento, un metodo o un parametro viene emesso fuori ordine.|  
|`MDMethodOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando viene emesso un metodo non ordinato.|  
|`MDFieldOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando un campo viene emesso senza ordine.|  
|`MDParamOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando un parametro viene emesso fuori ordine.|  
|`MDPropertyOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando una proprietà viene emessa senza ordine.|  
|`MDEventOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando viene generato un evento non ordinato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
