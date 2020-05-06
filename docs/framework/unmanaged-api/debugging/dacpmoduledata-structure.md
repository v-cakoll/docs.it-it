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
ms.openlocfilehash: e10d1792a8dc0b57ddd121ec09854e8e1824cade
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860797"
---
# <a name="dacpmoduledata-structure"></a>Struttura DacpModuleData

Definisce un buffer di trasporto per le informazioni di runtime di un modulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>Members

| Membro    | Descrizione                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Indirizzo dell'oggetto modulo.                                           |
| `File`    | Puntatore al file eseguibile di tipo PE.                       |
| `ilBase`  | Indirizzo della base dell'immagine caricata.                                 |
| `payLoad` | Buffer del payload per informazioni aggiuntive sul modulo utilizzate dal runtime. |

## <a name="remarks"></a>Osservazioni

Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Per usarlo, definire la struttura come specificato in precedenza.

## <a name="requirements"></a>Requisiti
**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Strutture di debug](debugging-structures.md)
