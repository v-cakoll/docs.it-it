---
title: Struttura DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d623fe862eaf5902fd89d0e512dd07f73a03246f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860813"
---
# <a name="dacpmethoddescdata-structure"></a>Struttura DacpMethodDescData

Definisce un buffer di trasporto per le informazioni di runtime di un metodo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a>Members

| Membro                       | Descrizione                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | Indica se il runtime dispone di codice nativo disponibile per l'istanza specificata del metodo. |
| `bIsDynamic`                 | Indica se il metodo viene generato in modo dinamico tramite la generazione di codice Lightweight.           |
| `wSlotNumber`                | Numero di slot del metodo nella tabella dei metodi.                                                   |
| `NativeCodeAddr`             | Indirizzo nativo iniziale del metodo.                                                            |
| `data`                       | Puntatore a un buffer usato internamente dal runtime.                                             |
| `MethodDescPtr`              | Puntatore a `MethodDesc` in fase di esecuzione.                                                     |
| `nativeCodeInfo`             | Puntatore a un buffer usato internamente dal runtime per tenere traccia dei metodi.                            |
| `moduleInfo`                 | Puntatore a un buffer usato internamente dal runtime per le informazioni sul modulo.                      |
| `MDToken`                    | Token associato al metodo specificato.                                                         |
| `payloadGC`                  | Puntatore a un buffer di Garbage Collection usato internamente dal runtime.                          |
| `payloadGC2`                 | Puntatore a un buffer di Garbage Collection usato internamente dal runtime.                          |
| `managedDynamicMethodObject` | Se il metodo è dinamico, il runtime usa questo buffer internamente per il rilevamento delle informazioni.     |
| `requestedIP`                | Utilizzato per popolare la struttura per ogni richiesta quando viene fornito un indirizzo di codice nativo.                    |
| `rejitDataCurrent`           | Informazioni sull'ultima versione instrumentata del metodo.                                   |
| `rejitDataRequested`         | ReJIT informazioni per l'indirizzo nativo richiesto.                                             |
| `cJittedRejitVersions`       | Numero di volte in cui il metodo è stato rejitted attraverso la strumentazione.                           |

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
- [Tipi di dati comuni](../common-data-types-unmanaged-api-reference.md)
