---
title: Struttura DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c0a12ab638adfccfb6406aa495bd3568911ee969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619779"
---
# <a name="dacpgetmoduleaddress-structure"></a>Struttura DacpGetModuleAddress

Definisce il contenitore per una richiesta del modulo di indirizzo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>Membri

| Membro      | Descrizione                |
| ----------- | -------------------------- |
| `ModulePtr` | Il puntatore al modulo. |

## <a name="methods"></a>Metodi

| Metodo                                                                                               | Descrizione                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Richiesta](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | Esegue una richiesta per popolare la struttura della struttura di runtime specificato. |

## <a name="remarks"></a>Note

Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria. Per usarlo, definire la struttura come specificato in precedenza, in cui `CLRDATA_ADDRESS` è un intero senza segno a 64 bit.

## <a name="requirements"></a>Requisiti
**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
