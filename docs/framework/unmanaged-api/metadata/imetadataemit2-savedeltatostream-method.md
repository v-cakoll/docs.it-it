---
title: Metodo IMetaDataEmit2::SaveDeltaToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: a8f46871dde4c664a502c261fc882f3badf0f362
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492754"
---
# <a name="imetadataemit2savedeltatostream-method"></a>Metodo IMetaDataEmit2::SaveDeltaToStream
Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pIStream`  
 in Puntatore di interfaccia al flusso scrivibile nel quale salvare le modifiche.  
  
 `dwSaveFlags`  
 [in] Riservato. Il valore deve essere zero.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
