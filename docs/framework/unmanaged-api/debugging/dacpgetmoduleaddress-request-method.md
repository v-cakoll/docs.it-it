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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179205"
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

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** **Nessuna libreria:** Nessuna  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfaccia DacpGetModuleAddress](dacpgetmoduleaddress-structure.md)
