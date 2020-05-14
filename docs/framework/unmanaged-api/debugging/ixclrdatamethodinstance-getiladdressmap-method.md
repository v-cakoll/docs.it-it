---
title: 'Metodo IXCLRDataMethodInstance:: GetILAddressMap'
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
ms.openlocfilehash: 7c4dcf59ce159434d5012120043f5bb548d49731
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396811"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a>Metodo IXCLRDataMethodInstance:: GetILAddressMap

Ottiene l'oggetto per l'indirizzamento delle informazioni di mapping.

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
in Lunghezza della matrice di mappe specificata.

`mapNeeded`\
out Numero di voci della mappa necessarie per il metodo.

`maps`\
[out, size_is (mapLen)] Matrice per l'archiviazione delle voci della mappa.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `IXCLRDataMethodInstance` interfaccia e corrisponde al quindicesimo slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
