---
title: Metodo IMetaDataTables::GetString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 41e7b8193ce3288d526db8d7d8c289b0a053ee4e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489756"
---
# <a name="imetadatatablesgetstring-method"></a>Metodo IMetaDataTables::GetString
Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito del riferimento corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ixString`  
 in Indice in corrispondenza del quale iniziare la ricerca del valore successivo.  
  
 `ppString`  
 out Puntatore a un puntatore al valore stringa restituito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables](imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](imetadatatables2-interface.md)
