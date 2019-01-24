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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea250cd413836796e8e6a3438ac7d6933035091e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714282"
---
# <a name="imetadatatables-interface"></a>Interfaccia IMetaDataTables
Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Ottiene un puntatore per l'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice di colonna specificata.|  
|[Metodo GetBlobHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Ottiene la dimensione, espressa in byte, dell'heap dei BLOB.|  
|[Metodo GetCodedTokenInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Ottiene un puntatore a una matrice dei token associato con l'indice di riga specificato.|  
|[Metodo GetColumn](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Ottiene un puntatore ai valori contenuti nella colonna in corrispondenza dell'indice di colonna specificata, nella tabella in corrispondenza dell'indice di tabella specificata.|  
|[Metodo GetColumnInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Ottiene i dati relativi alla colonna specificata nella tabella specificata.|  
|[Metodo GetGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Ottiene un GUID della riga in corrispondenza dell'indice specificato.|  
|[Metodo GetGuidHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Ottiene la dimensione, espressa in byte, dell'heap di GUID.|  
|[Metodo GetNextBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Ottiene l'indice del successivo BLOB nella tabella.|  
|[Metodo GetNextGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Ottiene l'indice del valore del GUID successivo nella colonna della tabella corrente.|  
|[Metodo GetNextString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Ottiene l'indice della stringa successiva nella colonna della tabella corrente.|  
|[Metodo GetNextUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Ottiene l'indice della riga che contiene la stringa a livello di codice successiva nella colonna della tabella corrente.|  
|[Metodo GetNumTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Ottiene il numero di tabelle nell'ambito dell'oggetto corrente `IMetaDataTables` istanza.|  
|[Metodo GetRow](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Ottiene la riga in corrispondenza dell'indice di riga specificata, nella tabella in corrispondenza dell'indice di tabella specificata.|  
|[Metodo GetString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Ottiene la stringa in corrispondenza dell'indice specificato della colonna di tabella presenti nell'ambito di riferimento corrente.|  
|[Metodo GetStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Ottiene la dimensione, espressa in byte, dell'heap delle stringhe.|  
|[Metodo GetTableIndex](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Ottiene l'indice per la tabella fa riferimento il token specificato.|  
|[Metodo GetTableInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Ottiene il nome, dimensioni delle righe, numero di righe, il numero di colonne e indice della colonna chiave della tabella in corrispondenza dell'indice di tabella specificata.|  
|[Metodo GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Ottiene la stringa a livello di codice in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.|  
|[Metodo GetUserStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Ottiene la dimensione, espressa in byte, dell'heap delle stringhe utente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
