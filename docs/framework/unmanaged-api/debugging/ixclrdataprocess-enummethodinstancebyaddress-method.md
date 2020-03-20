---
title: Metodo IXCLRDataProcess::EnumMethodInstanceByAddressIXCLRDataProcess::EnumMethodInstanceByAddress Method
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
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176656"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>Metodo IXCLRDataProcess::EnumMethodInstanceByAddressIXCLRDataProcess::EnumMethodInstanceByAddress Method

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
[in] Handle per l'enumerazione delle istanze del metodo.

`mod`\
[fuori] Istanza del metodo enumerato.

## <a name="remarks"></a>Osservazioni

Il metodo fornito fa `IXCLRDataProcess` parte dell'interfaccia e corrisponde al 28esimo slot della tabella dei metodi virtuali.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).
**Intestazione:** Nessuno **libreria:** nessuna versione di **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Interfaccia IXCLRDataProcess](ixclrdataprocess-interface.md)
