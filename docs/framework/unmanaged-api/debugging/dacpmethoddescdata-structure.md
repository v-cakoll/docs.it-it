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
ms.openlocfilehash: e9037fc035693e079e2471ad37263108656b8c01
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828608"
---
# <a name="dacpmethoddescdata-structure"></a>Struttura DacpMethodDescData

Definisce un buffer di trasporto per le informazioni di runtime del metodo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
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

## <a name="members"></a>Membri

| Membro                       | Descrizione                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | Indica se il runtime dispone di codice nativo disponibile per la creazione dell'istanza specificata del metodo. |
| `bIsDynamic`                 | Indica se il metodo viene generato in modo dinamico tramite la generazione di codice leggero.           |
| `wSlotNumber`                | Numero di slot del metodo nella tabella di metodo.                                                   |
| `NativeCodeAddr`             | Indirizzo nativo iniziale del metodo.                                                            |
| `data`                       | Puntatore a un buffer utilizzato internamente dal runtime.                                             |
| `MethodDescPtr`              | Puntatore al `MethodDesc` in fase di esecuzione.                                                     |
| `nativeCodeInfo`             | Puntatore a un buffer utilizzato internamente dal runtime per tenere traccia di metodi.                            |
| `moduleInfo`                 | Puntatore a un buffer utilizzato internamente dal runtime per informazioni sul modulo.                      |
| `MDToken`                    | Token associato al metodo specificato.                                                         |
| `payloadGC`                  | Puntatore a un buffer di raccolta garbage utilizzato internamente dal runtime.                          |
| `payloadGC2`                 | Puntatore a un buffer di raccolta garbage utilizzato internamente dal runtime.                          |
| `managedDynamicMethodObject` | Se il metodo dinamico, il runtime Usa internamente il buffer per le informazioni di rilevamento.     |
| `requestedIP`                | Utilizzato per popolare la struttura per ogni richiesta quando viene specificato un indirizzo di codice nativo.                    |
| `rejitDataCurrent`           | Informazioni sull'ultima versione instrumentata del metodo.                                   |
| `rejitDataRequested`         | ReJIT informazioni per l'indirizzo native richiesto.                                             |
| `cJittedRejitVersions`       | Numero di volte in cui che il metodo è stato rejitted tramite la strumentazione.                           |


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
- [Tipi di dati comuni](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
