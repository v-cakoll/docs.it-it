---
title: 'Metodo IXCLRDataMethodDefinition:: StartEnumInstances'
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
ms.openlocfilehash: 84e0ad392c5fee8377115427482d80543454fff3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397202"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>Metodo IXCLRDataMethodDefinition:: StartEnumInstances

Fornisce un handle per l'enumerazione delle istanze del metodo per un oggetto specificato `IXCLRDataAppDomain` .

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Parametri

`appDomain`\
in AppDomain per l'enumerazione.

`handle`\
out Handle per l'enumerazione delle istanze.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `IXCLRDataMethodDefinition` interfaccia e corrisponde al quinto slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
