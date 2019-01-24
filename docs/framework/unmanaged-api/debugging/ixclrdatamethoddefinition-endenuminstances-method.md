---
title: Metodo IXCLRDataMethodDefinition::EndEnumInstances
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
ms.openlocfilehash: 4a7cd8850778e9bbbc7d8d67f464c7787e40bc13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566096"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a>Metodo IXCLRDataMethodDefinition::EndEnumInstances

Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a>Parametri

`handle` [out] Handle per l'enumerazione delle istanze.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al quinto slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfaccia IXCLRDataMethodDefinition](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
