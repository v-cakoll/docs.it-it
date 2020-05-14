---
title: 'Metodo IXCLRDataModule:: Request'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 44ee4fc7fc2368b65f6f2fffe6ac239beddc6293
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395274"
---
# <a name="ixclrdatamodulerequest-method"></a>Metodo IXCLRDataModule:: Request

Richieste per popolare il buffer fornito con i dati del modulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a>Parametri

`reqCode`\
in Tipo di richiesta da inviare.

`inBufferSize`\
[in] dimensione del buffer di input da passare.

`inBuffer`\
[in, size_is (inBufferSize)] Puntatore del buffer per i dati non elaborati da inviare nella richiesta.

`outBufferSize`\
in Dimensioni del buffer di output.

`outBuffer`\
[out, size_is (outBufferSize)] Puntatore del buffer a usato per archiviare la risposta della richiesta.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `IXCLRDataModule` interfaccia e corrisponde allo slot 37a della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).
**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)
