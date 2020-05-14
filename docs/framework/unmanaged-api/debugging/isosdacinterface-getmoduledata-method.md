---
title: 'Metodo ISOSDacInterface:: GetModuleData'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 14e0eb812c84a0042150345d039451adf178caf1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396915"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>Metodo ISOSDacInterface:: GetModuleData

Recupera i dati corrispondenti al modulo caricato a un indirizzo specificato.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>Parametri

`moduleAddr`\
in Indirizzo del modulo per il quale recuperare le informazioni.

`data`\
out [Struttura DacpModuleData](dacpmoduledata-structure.md) che consente di conservare le informazioni del modulo caricato.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `ISOSDacInterface` interfaccia e corrisponde al quattordicesimo slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)
