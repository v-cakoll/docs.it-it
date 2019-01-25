---
title: Metodo IXCLRDataModule::Request
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
ms.openlocfilehash: 2cc712e6560fc58af7526428ba40c424be388eee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746661"
---
# <a name="ixclrdatamodulerequest-method"></a>Metodo IXCLRDataModule::Request

Richieste per popolare il buffer specificato con i dati del modulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a>Parametri

`reqCode` [in] Tipo per l'invio di richiesta.

`inBufferSize` [in] dimensione del buffer di input che deve essere passato.

`inBuffer` [in, size_is(inBufferSize)] Puntatore del buffer per i dati non elaborati da inviare nella richiesta.

`outBufferSize` [in] Dimensioni del buffer di output.

`outBuffer` [out, size_is(outBufferSize)] Puntatore del buffer usato per archiviare la risposta alla richiesta.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 36o slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno   
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfaccia IXCLRDataModule](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
