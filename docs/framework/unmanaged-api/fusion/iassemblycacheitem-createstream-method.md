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
ms.openlocfilehash: 0660621f465f2ba3610e06bd1df38baa1bc5c907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134481"
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

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** Fusion. h

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyCacheItem](iassemblycacheitem-interface.md)
