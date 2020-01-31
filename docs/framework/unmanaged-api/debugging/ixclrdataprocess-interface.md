---
title: Interfaccia IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790379"
---
# <a name="ixclrdataprocess-interface"></a>Interfaccia IXCLRDataProcess

Fornisce metodi per l'esecuzione di query sulle informazioni relative a un processo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Metodi

| Metodo                                                                                                                                               | Descrizione                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Ottiene un `AppDomain` in un processo in base al relativo ID univoco.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Fornisce un handle per enumerare i moduli di un processo.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Enumera i moduli di questo processo.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Rilascia le risorse usate dagli iteratori interni usati durante l'enumerazione del modulo.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Fornisce un handle per enumerare le istanze del metodo di `AppDomain` a partire da un indirizzo specificato. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Enumera le istanze del metodo di questo processo a partire da un offset di indirizzo.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.             |

## <a name="remarks"></a>Note

Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` che possono essere ottenuti tramite i normali meccanismi COM.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).   
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfacce di debug](debugging-interfaces.md)
