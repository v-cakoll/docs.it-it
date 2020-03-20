---
title: Metodo IMetaDataTables::GetColumn
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177132"
---
# <a name="imetadatatablesgetcolumn-method"></a>Metodo IMetaDataTables::GetColumn
Ottiene un puntatore al valore contenuto nella cella della colonna e della riga specificate nella tabella specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a>Parametri

 `ixTbl`  
 [in] Indice della tabella.  
  
 `ixCol`  
 [in] Indice della colonna nella tabella.  
  
 `rid`  
 [in] Indice della riga nella tabella.  
  
 `pVal`  
 [fuori] Puntatore al valore nella cella.  

## <a name="remarks"></a>Osservazioni

L'interpretazione del valore restituito `pVal` attraverso dipende dal tipo della colonna. Il tipo di colonna può essere determinato chiamando [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).

- Il **GetColumn** metodo converte automaticamente le colonne di tipo **Rid** o **CodedToken** in valori a 32 bit `mdToken` completi.
- Converte inoltre automaticamente valori a 8 o 16 bit in valori a 32 bit completi.
- Per le colonne di tipo *heap,* il *pVal* restituito sarà un indice nell'heap corrispondente.

| Tipo di colonna              | pVal contiene | Comment                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)  | mdToken     | *pVal* conterrà un Token completo. La funzione converte automaticamente il Rid in un token completo. |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | mdToken | Al ritorno, *pVal* conterrà un Token completo. La funzione decomprime automaticamente CodedToken in un token completo. |
| `iSHORT`(96)            | Int16         | Firma automaticamente fino a 32 bit.  |
| `iUSHORT`(97)           | UInt16        | Firma automaticamente fino a 32 bit.  |
| `iLONG`(98)             | Int32         |                                        |
| `iULONG`(99)            | UInt32        |                                        |
| `iBYTE`(100)            | Byte          | Firma automaticamente fino a 32 bit.  |
| `iSTRING`(101)          | Indice heap stringhe | *pVal* è un indice nell'heap delle stringhe. Usare [IMetadataTables::GetString](imetadatatables-getstring-method.md) per ottenere il valore String della colonna effettiva. |
| `iGUID`(102)            | Indice heap guid | *pVal* è un indice nell'heap Guid. Usare [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) per ottenere il valore Guid della colonna effettiva. |
| `iBLOB`(103)            | Indice heap BLOB | *pVal* è un indice nell'heap Blob.pVal is an index into the Blob heap. Usare [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) per ottenere il valore BLOB della colonna effettiva. |
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 Versioni di **.NET Framework**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
