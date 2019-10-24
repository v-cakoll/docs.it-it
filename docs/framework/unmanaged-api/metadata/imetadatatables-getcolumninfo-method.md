---
title: Metodo IMetaDataTables::GetColumnInfo
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd67d9faafedf4fb92c69618d4464ebb2ce47dcc
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774250"
---
# <a name="imetadatatablesgetcolumninfo-method"></a>Metodo IMetaDataTables::GetColumnInfo
Ottiene i dati relativi alla colonna specificata nella tabella specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a>Parametri
=======

 `ixTbl`  
 in Indice della tabella desiderata.  
  
 `ixCol`  
 in Indice della colonna desiderata.  
  
 `poCol`  
 out Puntatore all'offset della colonna nella riga.  
  
 `pcbCol`  
 out Puntatore alla dimensione, in byte, della colonna.  
  
 `pType`  
 out Puntatore al tipo dei valori nella colonna.  
  
 `ppName`  
 out Puntatore a un puntatore al nome della colonna.  
 
## <a name="remarks"></a>Note

Il tipo di colonna restituito rientra in un intervallo di valori:

| pType                    | Descrizione   | Funzione helper                   |
|--------------------------|---------------|-----------------------------------|
| `0`.. `iRidMax`<br>(0.. 63)   | Sbarazzarsi           | **IsRidType**<br>**IsRidOrToken** |
| `iCodedToken`.. `iCodedTokenMax`<br>(64.. 95) | Token codificato | **IsCodedTokenType** <br>**IsRidOrToken** |
| `iSHORT` (96)            | Int16         | **IsFixedType**                   |
| `iUSHORT` (97)           | UInt16        | **IsFixedType**                   |
| `iLONG` (98)             | Int32         | **IsFixedType**                   |
| `iULONG` (99)            | UInt32        | **IsFixedType**                   |
| `iBYTE` (100)            | Byte          | **IsFixedType**                   |
| `iSTRING` (101)          | Stringa        | **IsHeapType**                    |
| `iGUID` (102)            | GUID          | **IsHeapType**                    |
| `iBLOB` (103)            | Blob          | **IsHeapType**                    |

I valori archiviati nell' *heap* (ovvero `IsHeapType == true`) possono essere letti utilizzando:

- `iSTRING`: **IMetadataTables. GetString**
- `iGUID`: **IMetadataTables. GETguid**
- `iBLOB`: **IMetadataTables. GetBlob**

> [!IMPORTANT]
> Per usare le costanti definite nella tabella precedente, includere la direttiva `#define _DEFINE_META_DATA_META_CONSTANTS` fornita dal file di intestazione *cor. h* .

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
