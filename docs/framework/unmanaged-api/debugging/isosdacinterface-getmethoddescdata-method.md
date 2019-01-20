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
ms.openlocfilehash: 3f22752446413c622a20340541b0ac328f63c77b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416731"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Metodo ISOSDacInterface::GetMethodDescData

Ottiene i dati per il dato [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    void                       *data,
    ULONG                      cRevertedRejitVersions,
    void                      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a>Parametri

`methodDesc` [in] L'indirizzo del MethodDesc.

`ip` [in] L'indirizzo IP del metodo.

`data` [out] I dati associati con la MethodDesc come restituito dall'API interne. La struttura deve almeno 168 byte.

`cRevertedRejitVersions` [out] Il numero di versioni rejit ripristinato.

`rgRevertedRejitData` [out] I dati associati con le versioni rejit ripristinato come restituito dall'API interne. La struttura deve almeno 24 byte.

`pcNeededRevertedRejitData` [out] Il numero di byte necessari per archiviare i dati associati con le versioni ReJit ripristinate.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale. Anche il `CLRDATA_ADDRESS` sono valori integer senza segno a 64 bit.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfaccia ISOSDacInterface](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
