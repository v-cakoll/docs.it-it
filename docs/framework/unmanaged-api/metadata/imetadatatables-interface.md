---
title: Interfaccia IMetaDataTables
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 17305f2c088dd6f479da4c823d3db0fd50c0b3d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443229"
---
# <a name="imetadatatables-interface"></a>Interfaccia IMetaDataTables
Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Ottiene un puntatore all'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice di colonna specificato.|  
|[Metodo GetBlobHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap BLOB.|  
|[Metodo GetCodedTokenInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Ottiene un puntatore a una matrice di token associati all'indice di riga specificato.|  
|[Metodo GetColumn](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Ottiene un puntatore ai valori contenuti nella colonna in corrispondenza dell'indice di colonna specificato, nella tabella in corrispondenza dell'indice di tabella specificato.|  
|[Metodo GetColumnInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Ottiene i dati relativi alla colonna specificata nella tabella specificata.|  
|[Metodo GetGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Ottiene un GUID dalla riga in corrispondenza dell'indice specificato.|  
|[Metodo GetGuidHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap GUID.|  
|[Metodo GetNextBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Ottiene l'indice del BLOB successivo nella tabella.|  
|[Metodo GetNextGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Ottiene l'indice del valore GUID successivo nella colonna della tabella corrente.|  
|[Metodo GetNextString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Ottiene l'indice della stringa successiva nella colonna della tabella corrente.|  
|[Metodo GetNextUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.|  
|[Metodo GetNumTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Ottiene il numero di tabelle nell'ambito dell'istanza di `IMetaDataTables` corrente.|  
|[Metodo GetRow](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Ottiene la riga in corrispondenza dell'indice di riga specificato, nella tabella in corrispondenza dell'indice di tabella specificato.|  
|[Metodo GetString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito del riferimento corrente.|  
|[Metodo GetStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap delle stringhe.|  
|[Metodo GetTableIndex](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Ottiene l'indice per la tabella a cui fa riferimento il token specificato.|  
|[Metodo GetTableInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Ottiene il nome, le dimensioni della riga, il numero di righe, il numero di colonne e l'indice della colonna chiave della tabella in corrispondenza dell'indice di tabella specificato.|  
|[Metodo GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Ottiene la stringa hardcoded in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.|  
|[Metodo GetUserStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap delle stringhe utente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
