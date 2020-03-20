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
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177126"
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
 [in] Indice della tabella desiderata.  
  
 `ixCol`  
 [in] Indice della colonna desiderata.  
  
 `poCol`  
 [fuori] Puntatore all'offset della colonna nella riga.  
  
 `pcbCol`  
 [fuori] Puntatore alla dimensione, in byte, della colonna.  
  
 `pType`  
 [fuori] Puntatore al tipo di valori nella colonna.  
  
 `ppName`  
 [fuori] Puntatore a un puntatore al nome della colonna.  

## <a name="remarks"></a>Osservazioni

Il tipo di colonna restituito rientra in un intervallo di valori:The returned column type falls within a range of values:

| pTipo                    | Descrizione   | Funzione di supporto                   |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)   | liberarsi           | **IsRidType (tipo in stato di diridtype**<br>**Token IsRidOrToken** |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | Token codificato | **IsCodedTokenType** <br>**Token IsRidOrToken** |
| `iSHORT`(96)            | Int16         | **IsFixedType (Tipo di oggetto)**                   |
| `iUSHORT`(97)           | UInt16        | **IsFixedType (Tipo di oggetto)**                   |
| `iLONG`(98)             | Int32         | **IsFixedType (Tipo di oggetto)**                   |
| `iULONG`(99)            | UInt32        | **IsFixedType (Tipo di oggetto)**                   |
| `iBYTE`(100)            | Byte          | **IsFixedType (Tipo di oggetto)**                   |
| `iSTRING`(101)          | string        | **IsHeapType (Tipo IsHeap)**                    |
| `iGUID`(102)            | Guid          | **IsHeapType (Tipo IsHeap)**                    |
| `iBLOB`(103)            | BLOB          | **IsHeapType (Tipo IsHeap)**                    |

I valori archiviati nell'heap, `IsHeapType == true`ovvero , possono essere letti utilizzando: *heap*

- `iSTRING`: **IMetadataTables.GetString**
- `iGUID`: **IMetadataTables.GetGUID**
- `iBLOB`: **IMetadataTables.GetBlob**

> [!IMPORTANT]
> Per utilizzare le costanti definite nella tabella `#define _DEFINE_META_DATA_META_CONSTANTS` precedente, includere la direttiva fornita dal file di intestazione *cor.h.*

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
