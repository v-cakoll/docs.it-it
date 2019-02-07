---
title: Struttura DacpModuleData
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: db3fdaa768e3d1b445f08c3964521570631f0965
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828667"
---
# <a name="dacpmoduledata-structure"></a>Struttura DacpModuleData

Definisce un buffer di trasporto per le informazioni di runtime del modulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>Membri

| Membro    | Descrizione                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Indirizzo dell'oggetto modulo.                                           |
| `File`    | Un puntatore al file eseguibile portabile (PE).                       |
| `ilBase`  | Base dell'indirizzo dell'immagine caricata.                                 |
| `payLoad` | Un buffer di payload per informazioni sul modulo aggiuntiva utilizzate dal runtime. |


## <a name="remarks"></a>Note

Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria. Per usarlo, definire la struttura come specificato in precedenza.

## <a name="requirements"></a>Requisiti
**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
