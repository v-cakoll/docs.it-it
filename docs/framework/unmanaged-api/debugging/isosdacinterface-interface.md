---
title: Interfaccia ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 94349a3f7b18c8ce29bb3a71cb9d10ee4eac8036
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790471"
---
# <a name="isosdacinterface-interface"></a>Interfaccia ISOSDacInterface

Fornisce metodi helper per accedere ai dati da `SOS`.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Metodi

| Metodo                                                                                                               | Descrizione                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [GetMethodDescData](isosdacinterface-getmethoddescdata-method.md) | Ottiene i dati per il puntatore MethodDesc specificato. |
| [GetMethodDescPtrFromIP](isosdacinterface-getmethoddescptrfromip-method.md) | Recupera il puntatore di MethodDesc corrispondente al metodo che contiene l'indirizzo di istruzione nativo specificato. |
| [GetModuleData](isosdacinterface-getmoduledata-method.md)| Recupera i dati corrispondenti al modulo caricato a un indirizzo specificato. |

## <a name="remarks"></a>Note

Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` che possono essere ottenuti tramite i normali meccanismi COM.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfacce di debug](debugging-interfaces.md)
