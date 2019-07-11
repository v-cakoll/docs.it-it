---
title: Metodo IXCLRDataMethodInstance::GetILAddressMap
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 66e4768acff7ab735c6ac9e8f8f51a9511f7e371
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744691"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a>Metodo IXCLRDataMethodInstance::GetILAddressMap

Ottiene il livello di integrità per le informazioni di mapping di indirizzi.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a>Parametri

`mapLen`\
[in] La lunghezza della matrice di mappe fornito.

`mapNeeded`\
[out] Il numero di voci della mappa che desideri nel metodo.

`maps`\
[out, size_is(mapLen)] La matrice per archiviare le voci della mappa.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `IXCLRDataMethodInstance` interfaccia e corrisponde al 14 slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuna  
**Libreria:** Nessuna  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
