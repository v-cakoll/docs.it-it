---
title: Interfaccia IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c8d6e36687fd43bbc59304eee64dd42eb78101e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676523"
---
# <a name="ixclrdatamodule-interface"></a>Interfaccia IXCLRDataModule

Fornisce metodi per la ricerca delle informazioni su un modulo caricato.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Metodi

| Metodo                                                                                                                                | Descrizione                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Ottiene la definizione del metodo corrispondente a un token di metadati specificato. |
| [Richiesta](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | Richieste per popolare il buffer specificato con i dati del modulo.       |
| [GetVersionId](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | Ottiene l'ID della versione. del modulo                                       |

## <a name="remarks"></a>Note

Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria. Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` che può essere ottenuto tramite i normali meccanismi di COM.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
