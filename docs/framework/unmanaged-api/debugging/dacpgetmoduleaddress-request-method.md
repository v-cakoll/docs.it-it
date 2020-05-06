---
title: Metodo DacpGetModuleAddress::Request
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860846"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>Metodo DacpGetModuleAddress::Request

Esegue una richiesta per popolare la struttura dalla struttura di runtime specificata.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Parametri

`pDataModule`\
in Puntatore al modulo dati di inizializzazione.

## <a name="remarks"></a>Osservazioni

Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Per usarlo, il modo più semplice consiste nel simulare l'implementazione:

- Restituisce il valore ottenuto dalla chiamata al `Request` metodo sul `IXCLRDataModule*` parametro con i parametri seguenti:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere i [requisiti di sistema](../../get-started/system-requirements.md)\
**Intestazione:** Nessuno
**Libreria:** Nessuno
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Struttura DacpGetModuleAddress](dacpgetmoduleaddress-structure.md)
