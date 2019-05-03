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
ms.openlocfilehash: 628ca1b555d80319312450d784981cfed1bda947
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045994"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>Enumerazione CorErrorIfEmitOutOfOrder
Contiene valori di flag che indicano in quali condizioni è necessario generare un messaggio di errore per notificare che i metadati sono stati emessi senza ordine.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
