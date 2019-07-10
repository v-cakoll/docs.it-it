---
title: Metodo ISOSDacInterface::GetMethodDescData
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
ms.openlocfilehash: ea54fdd83b9470db4a08daceaa695e450f5ca1af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764817"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Metodo ISOSDacInterface::GetMethodDescData

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
[in] L'indirizzo del MethodDesc.

`ip`\
[in] L'indirizzo IP del metodo.

`data`\
[out] I dati associati con la MethodDesc come restituito dall'API interne.

`cRevertedRejitVersions`\
[out] Il numero di versioni rejit ripristinato.

`rgRevertedRejitData`\
[out] I dati associati con le versioni rejit ripristinato come restituito dall'API interne.

`pcNeededRevertedRejitData`\
[out] Il numero di byte necessari per archiviare i dati associati con le versioni ReJit ripristinate.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale. Per poter utilizzarli [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) deve essere definito come un intero senza segno a 64 bit.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)
