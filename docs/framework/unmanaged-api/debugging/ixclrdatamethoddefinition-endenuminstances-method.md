---
title: 'Metodo IXCLRDataMethodDefinition:: EndEnumInstances'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: febe6766c7a35228820421eee975c777988efd1f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396496"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a>Metodo IXCLRDataMethodDefinition:: EndEnumInstances

Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Parametri

`handle`\
out Handle per l'enumerazione delle istanze.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `IXCLRDataMethodDefinition` interfaccia e corrisponde al settimo slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
