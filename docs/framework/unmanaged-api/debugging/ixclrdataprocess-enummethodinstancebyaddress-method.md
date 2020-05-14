---
title: 'Metodo IXCLRDataProcess:: EnumMethodInstanceByAddress'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: f3800a5980304394dd648111fe23a3bb0890c575
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395115"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>Metodo IXCLRDataProcess:: EnumMethodInstanceByAddress

Enumera le istanze del metodo di questo processo a partire da un offset di indirizzo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a>Parametri

`handle`\
in Handle per l'enumerazione delle istanze del metodo.

`mod`\
out Istanza del metodo enumerata.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al ventinovesimo slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).
**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vedi anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Interfaccia IXCLRDataProcess](ixclrdataprocess-interface.md)
