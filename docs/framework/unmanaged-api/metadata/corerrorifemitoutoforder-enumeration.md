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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16f6d7bf6fa1730d50cfe81526817e492a453dad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781977"
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Indica il comportamento predefinito, che non genera messaggi di errore.|  
|`MDErrorOutOfOrderNone`|Indica che il compilatore non deve generare i messaggi di errore.|  
|`MDErrorOutOfOrderAll`|Indica che il compilatore deve generare un messaggio di errore quando un campo, proprietà, eventi, metodo o parametro viene generato nell'ordine errato.|  
|`MDMethodOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando un metodo viene generato nell'ordine errato.|  
|`MDFieldOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando un campo viene generato nell'ordine errato.|  
|`MDParamOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando un parametro viene generato nell'ordine errato.|  
|`MDPropertyOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando una proprietà viene emessa fuori sequenza.|  
|`MDEventOutOfOrder`|Indica che il compilatore deve generare un messaggio di errore quando viene generato un evento non in ordine.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
