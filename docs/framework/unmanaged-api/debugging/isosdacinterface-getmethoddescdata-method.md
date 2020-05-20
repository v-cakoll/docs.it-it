---
title: 'Metodo ISOSDacInterface:: GetMethodDescData'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421020"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Metodo ISOSDacInterface:: GetMethodDescData

Ottiene i dati per il puntatore MethodDesc specificato.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a>Parametri

`methodDesc`\
in Indirizzo di MethodDesc.

`ip`\
in Indirizzo IP del metodo.

`data`\
out Dati associati a MethodDesc restituiti dalle API interne.

`cRevertedRejitVersions`\
out Numero di versioni di ReJIT ripristinate.

`rgRevertedRejitData`\
out I dati associati alle versioni ReJIT ripristinate restituite dalle API interne.

`pcNeededRevertedRejitData`\
out Numero di byte necessari per archiviare i dati associati alle versioni di ReJit ripristinate.

## <a name="remarks"></a>Osservazioni

Il metodo fornito fa parte dell' `ISOSDacInterface` interfaccia e corrisponde al ventunesimo slot della tabella del metodo virtuale. Per poterli utilizzare, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) è necessario definire come Unsigned Integer a 64 bit.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)
