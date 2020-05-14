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
ms.openlocfilehash: e4c44379d9db0f5e98f3ca66ec0486961ec2df3a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396940"
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

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `ISOSDacInterface` interfaccia e corrisponde al ventunesimo slot della tabella del metodo virtuale. Per poterli utilizzare, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) è necessario definire come Unsigned Integer a 64 bit.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)
