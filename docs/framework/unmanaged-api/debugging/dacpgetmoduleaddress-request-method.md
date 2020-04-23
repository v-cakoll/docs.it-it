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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102907"
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
[in] Puntatore al modulo dati di serie.

## <a name="remarks"></a>Osservazioni

Questa struttura si trova all'interno del runtime e non viene esposta tramite intestazioni o file di libreria. Per usarlo, il modo più semplice è quello di imitare l'implementazione:

- Restituire il valore ottenuto chiamando il `Request` metodo sul `IXCLRDataModule*` parametro con i seguenti parametri:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md)\
**Intestazione:** Nessuno
**Biblioteca:** Nessuno
Versioni di **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [DacpGetModuleAddress (struttura)](dacpgetmoduleaddress-structure.md)
