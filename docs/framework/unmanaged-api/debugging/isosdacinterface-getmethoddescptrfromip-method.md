---
title: 'Metodo ISOSDacInterface:: GetMethodDescPtrFromIP'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396932"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>Metodo ISOSDacInterface:: GetMethodDescPtrFromIP

Recupera il puntatore di MethodDesc corrispondente al metodo che contiene l'indirizzo di istruzione nativo specificato.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a>Parametri

`ip`\
in Un indirizzo all'interno del metodo in fase di esecuzione.

`ppMD`\
out Indirizzo dell'oggetto `MethodDesc` per il metodo specifico.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' [ `ISOSDacInterface` interfaccia](isosdacinterface-interface.md) e corrisponde al ventiduesimo slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)
