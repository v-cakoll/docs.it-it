---
title: 'Metodo IXCLRDataProcess:: EndEnumMethodInstancesByAddress'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 04ce8f44b0c9f532951666de7bfb9de475c14746
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395250"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a>Metodo IXCLRDataProcess:: EndEnumMethodInstancesByAddress

Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Parametri

`handle`\
out Handle per l'enumerazione delle istanze del metodo.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al trentesimo slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Interfaccia IXCLRDataProcess](ixclrdataprocess-interface.md)
