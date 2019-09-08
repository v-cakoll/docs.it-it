---
title: Metodo IAssemblyCacheItem::CreateStream
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af7dc4e1694b66fc4a5ce37e515c71e9fa3db49
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796737"
---
# <a name="iassemblycacheitemcreatestream-method"></a>Metodo IAssemblyCacheItem::CreateStream

Crea un flusso con il nome e il formato specificati.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a>Parametri

`dwFlags`\
in Flag definiti in Fusion. idl.

`pszStreamName`\
in Nome del flusso da creare.

`dwFormat`\
in Formato del file da trasmettere.

`dwFormatFlags`\
in Flag specifici del formato definiti in Fusion. idl.

`ppIStream`\
out Puntatore all'indirizzo dell'istanza di [IStream](/windows/desktop/api/objidl/nn-objidl-istream) restituita.

`puliMaxSize`\
[in, facoltativo] Dimensione massima del flusso a cui fa riferimento `ppIStream`.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** Fusion. h

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyCacheItem](iassemblycacheitem-interface.md)
