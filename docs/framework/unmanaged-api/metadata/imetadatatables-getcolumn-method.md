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
ms.openlocfilehash: 376b9ff09ad38ca43d57fcf064458e0331da8aad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442007"
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
 in Indice della tabella.  
  
 `ixCol`  
 in Indice della colonna nella tabella.  
  
 `rid`  
 in Indice della riga nella tabella.  
  
 `pVal`  
 out Puntatore al valore nella cella.  
 
## <a name="remarks"></a>Note

L'interpretazione del valore restituito tramite `pVal` dipende dal tipo della colonna. Il tipo di colonna può essere determinato chiamando [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).

- Il metodo **GetColumn** converte automaticamente le colonne di tipo **RID** o **CodedToken** in valori di `mdToken` a 32 bit completi.
- Converte inoltre automaticamente i valori a 8 bit o a 16 bit in valori completi a 32 bit. 
- Per le colonne di tipo *heap* , il valore di *pval* restituito sarà un indice nell'heap corrispondente.

| Tipo di colonna              | pVal contiene | Commento                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)  | mdToken     | *pval* conterrà un token completo. La funzione converte automaticamente il RID in un token completo. |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | mdToken | Al ritorno, *pval* conterrà un token completo. La funzione decomprime automaticamente il CodedToken in un token completo. |
| `iSHORT` (96)            | Int16         | Firma automaticamente estesa a 32 bit.  |
| `iUSHORT` (97)           | UInt16        | Firma automaticamente estesa a 32 bit.  |
| `iLONG` (98)             | Int32         |                                        | 
| `iULONG` (99)            | UInt32        |                                        |
| `iBYTE` (100)            | Byte          | Firma automaticamente estesa a 32 bit.  |
| `iSTRING` (101)          | Indice dell'heap delle stringhe | *pval* è un indice nell'heap delle stringhe. Usare [IMetadataTables:: GetString](imetadatatables-getstring-method.md) per ottenere il valore della stringa di colonna effettivo. |
| `iGUID` (102)            | Indice heap GUID | *pval* è un indice nell'heap GUID. Usare [IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) per ottenere il valore effettivo del GUID della colonna. |
| `iBLOB` (103)            | Indice heap BLOB | *pval* è un indice nell'heap BLOB. Usare [IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) per ottenere il valore effettivo del BLOB della colonna. |
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **.NET Framework versioni** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
