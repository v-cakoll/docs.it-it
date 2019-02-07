---
title: Metodo IXCLRDataMethodInstance::GetRepresentativeEntryAddress
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
ms.openlocfilehash: 52b2fdaaefd16a49300641f44041b8352141385b
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828677"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>Metodo IXCLRDataMethodInstance::GetRepresentativeEntryAddress

Ottiene l'indirizzo del punto di ingresso più significativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

### <a name="parameters"></a>Parametri

`addr` [out] L'indirizzo del punto di ingresso nativo più rappresentativo per il metodo.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di [ `IXCLRDataMethodInstance` interfaccia](ixclrdatamethodinstance-interface.md) e corrisponde al 19 slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfaccia IXCLRDataMethodInstance](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
