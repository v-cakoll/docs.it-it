---
title: Metodo IMetaDataTables::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 5936ca837c9ab452e992fcb09aacb476ab37316a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431427"
---
# <a name="imetadatatablesgetuserstring-method"></a>Metodo IMetaDataTables::GetUserString

Ottiene la stringa hardcoded in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a>Parametri

`ixUserString`\
in Valore di indice da cui verrà recuperata la stringa hardcoded.

`pcbData`\
out Puntatore alla dimensione del `ppData`.

`ppData`\
out Puntatore a un puntatore alla stringa restituita.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** Cor. h

**Libreria:** Usato come risorsa in MsCorEE. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables](imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](imetadatatables2-interface.md)
