---
title: Metodo ISOSDacInterface::GetModuleData
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
ms.openlocfilehash: 128af261c429228c97d952f1f8d382f46306f711
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229316"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>Metodo ISOSDacInterface::GetModuleData

Recupera i dati corrispondenti al modulo caricato in un determinato indirizzo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>Parametri

`moduleAddr`\
[in] L'indirizzo del modulo per recuperare informazioni per.

`data`\
[out] Il [DacpModuleData struttura](dacpmoduledata-structure.md) per contenere le informazioni del modulo caricato.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `ISOSDacInterface` interfaccia e corrisponde al 13 slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)