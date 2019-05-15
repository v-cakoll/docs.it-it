---
title: Metodo IXCLRDataMethodDefinition::StartEnumInstances
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7f45a5b13e767fa6849f307ee96fb822447f1263
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629960"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>Metodo IXCLRDataMethodDefinition::StartEnumInstances

Fornisce un handle per l'enumerazione delle istanze di metodo per un determinato `IXCLRDataAppDomain`.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Parametri

`appDomain`\
[in] Un dominio di applicazione per l'enumerazione.

`handle`\
[out] Handle per l'enumerazione delle istanze.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al terzo slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
