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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178367"
---
# <a name="ixclrdataprocess-interface"></a>Interfaccia IXCLRDataProcess

Fornisce metodi per l'esecuzione di query su informazioni su un processo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Metodi

| Metodo                                                                                                                                               | Descrizione                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Ottiene `AppDomain` un oggetto in un processo in base al relativo ID univoco.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Fornisce un handle per enumerare i moduli di un processo.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Enumera i moduli di questo processo.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione del modulo.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Fornisce un handle per enumerare le istanze del metodo a `AppDomain` partire da un indirizzo specificato. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Enumera le istanze del metodo di questo processo a partire da un offset di indirizzo.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.             |

## <a name="remarks"></a>Osservazioni

Questa interfaccia si trova all'interno del runtime e non viene esposta tramite intestazioni o file di libreria. Tuttavia, è un'interfaccia COM `IUnknown` che `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` deriva da con GUID che può essere ottenuto tramite i normali meccanismi COM.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).
**Intestazione:** Nessuno  
**Biblioteca:** Nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfacce di debug](debugging-interfaces.md)
