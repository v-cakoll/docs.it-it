---
title: Interfaccia IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790431"
---
# <a name="ixclrdatamethoddefinition-interface"></a>Interfaccia IXCLRDataMethodDefinition

Fornisce metodi per eseguire query sulle informazioni relative a una definizione di metodo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Metodi

Di seguito sono riportati alcuni dei metodi disponibili nell'interfaccia.

| Metodo                                                                                                                          | Descrizione                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [StartEnumInstances](ixclrdatamethoddefinition-startenuminstances-method.md) | Fornisce un handle per l'enumerazione delle istanze del metodo per un determinato `IXCLRDataAppDomain`. |
| [EnumInstance](ixclrdatamethoddefinition-enuminstance-method.md)             | Enumera le istanze di questa definizione di metodo.                                         |
| [EndEnumInstances](ixclrdatamethoddefinition-endenuminstances-method.md)     | Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.         |

## <a name="remarks"></a>Note

Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` che possono essere ottenuti tramite i normali meccanismi COM.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfacce di debug](debugging-interfaces.md)
