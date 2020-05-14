---
title: 'Metodo IXCLRDataMethodInstance:: GetRepresentativeEntryAddress'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395747"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>Metodo IXCLRDataMethodInstance:: GetRepresentativeEntryAddress

Ottiene l'indirizzo del punto di ingresso più rappresentativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a>Parametri

`addr`\
out Indirizzo del punto di ingresso nativo più rappresentativo per il metodo.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' [ `IXCLRDataMethodInstance` interfaccia](ixclrdatamethodinstance-interface.md) e corrisponde al ventesimo slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
