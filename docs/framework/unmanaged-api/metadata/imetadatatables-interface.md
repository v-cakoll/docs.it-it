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
ms.openlocfilehash: 2105033e684ec172e24adfb14bcab7668b388af3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501121"
---
# <a name="imetadatatables-interface"></a>Interfaccia IMetaDataTables
Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBlob](imetadatatables-getblob-method.md)|Ottiene un puntatore all'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice di colonna specificato.|  
|[Metodo GetBlobHeapSize](imetadatatables-getblobheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap BLOB.|  
|[Metodo GetCodedTokenInfo](imetadatatables-getcodedtokeninfo-method.md)|Ottiene un puntatore a una matrice di token associati all'indice di riga specificato.|  
|[Metodo GetColumn](imetadatatables-getcolumn-method.md)|Ottiene un puntatore ai valori contenuti nella colonna in corrispondenza dell'indice di colonna specificato, nella tabella in corrispondenza dell'indice di tabella specificato.|  
|[Metodo GetColumnInfo](imetadatatables-getcolumninfo-method.md)|Ottiene i dati relativi alla colonna specificata nella tabella specificata.|  
|[Metodo GetGuid](imetadatatables-getguid-method.md)|Ottiene un GUID dalla riga in corrispondenza dell'indice specificato.|  
|[Metodo GetGuidHeapSize](imetadatatables-getguidheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap GUID.|  
|[Metodo GetNextBlob](imetadatatables-getnextblob-method.md)|Ottiene l'indice del BLOB successivo nella tabella.|  
|[Metodo GetNextGuid](imetadatatables-getnextguid-method.md)|Ottiene l'indice del valore GUID successivo nella colonna della tabella corrente.|  
|[Metodo GetNextString](imetadatatables-getnextstring-method.md)|Ottiene l'indice della stringa successiva nella colonna della tabella corrente.|  
|[Metodo GetNextUserString](imetadatatables-getnextuserstring-method.md)|Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.|  
|[Metodo GetNumTables](imetadatatables-getnumtables-method.md)|Ottiene il numero di tabelle nell'ambito dell' `IMetaDataTables` istanza corrente.|  
|[Metodo GetRow](imetadatatables-getrow-method.md)|Ottiene la riga in corrispondenza dell'indice di riga specificato, nella tabella in corrispondenza dell'indice di tabella specificato.|  
|[Metodo GetString](imetadatatables-getstring-method.md)|Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito del riferimento corrente.|  
|[Metodo GetStringHeapSize](imetadatatables-getstringheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap delle stringhe.|  
|[Metodo GetTableIndex](imetadatatables-gettableindex-method.md)|Ottiene l'indice per la tabella a cui fa riferimento il token specificato.|  
|[Metodo GetTableInfo](imetadatatables-gettableinfo-method.md)|Ottiene il nome, le dimensioni della riga, il numero di righe, il numero di colonne e l'indice della colonna chiave della tabella in corrispondenza dell'indice di tabella specificato.|  
|[Metodo GetUserString](imetadatatables-getuserstring-method.md)|Ottiene la stringa hardcoded in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.|  
|[Metodo GetUserStringHeapSize](imetadatatables-getuserstringheapsize-method.md)|Ottiene la dimensione, in byte, dell'heap delle stringhe utente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataTables2](imetadatatables2-interface.md)
