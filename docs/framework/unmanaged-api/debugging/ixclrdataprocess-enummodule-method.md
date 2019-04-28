---
title: Metodo IXCLRDataProcess::EnumModule
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a0398d18f9568754231082d63b4c6a2c865d8c6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775265"
---
# <a name="ixclrdataprocessenummodule-method"></a>Metodo IXCLRDataProcess::EnumModule

Enumera i moduli di questo processo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a>Parametri

`handle`\
[in, out] Handle per l'enumerazione dei moduli.

`mod`\
[out] Il modulo enumerato.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 25 slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)
- [IXCLRDataProcess Interface](ixclrdataprocess-interface.md)
