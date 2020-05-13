---
title: Interfaccia ICorDebugProcess4
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213582"
---
# <a name="icordebugprocess4-interface"></a>Interfaccia ICorDebugProcess4

Fornisce supporto per il controllo dell'esecuzione out-of-process.

## <a name="methods"></a>Metodi

| Metodo                                                                 | Descrizione                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) | Notifica alla pipeline ICorDebug che il debugger out-of-process sta continuando l'esecuzione del debug. |

## <a name="remarks"></a>Osservazioni

Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` che è possibile ottenere tramite i normali meccanismi com.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** Nessuno

**Libreria:** Nessuno

**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
