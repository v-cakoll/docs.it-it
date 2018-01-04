---
title: Interfaccia IMetaDataTables
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables
helpviewer_keywords: IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff70e99a963c929792a73cefd6e8feaefa8b252e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatables-interface"></a>Interfaccia IMetaDataTables
Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Ottiene un puntatore per l'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice della colonna specificata.|  
|[Metodo GetBlobHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap BLOB.|  
|[Metodo GetCodedTokenInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Ottiene un puntatore a una matrice di token associato all'indice di riga specificato.|  
|[Metodo GetColumn](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Ottiene un puntatore ai valori contenuti nella colonna in corrispondenza dell'indice di colonna specificata, nella tabella in corrispondenza dell'indice di tabella specificata.|  
|[Metodo GetColumnInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Ottiene i dati relativi alla colonna specificata nella tabella specificata.|  
|[Metodo GetGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Ottiene un GUID della riga in corrispondenza dell'indice specificato.|  
|[Metodo GetGuidHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap dei GUID.|  
|[Metodo GetNextBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Ottiene l'indice del successivo BLOB nella tabella.|  
|[Metodo GetNextGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Ottiene l'indice del successivo valore GUID nella colonna della tabella corrente.|  
|[Metodo GetNextString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Ottiene l'indice della stringa successiva nella colonna della tabella corrente.|  
|[Metodo GetNextUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.|  
|[Metodo GetNumTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Ottiene il numero di tabelle nell'ambito dell'oggetto corrente `IMetaDataTables` istanza.|  
|[Metodo GetRow](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Ottiene la riga in corrispondenza dell'indice di riga specificata, nella tabella in corrispondenza dell'indice di tabella specificata.|  
|[Metodo GetString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito di riferimento corrente.|  
|[Metodo GetStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap delle stringhe.|  
|[Metodo GetTableIndex](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Ottiene l'indice per la tabella a cui fa riferimento il token specificato.|  
|[Metodo GetTableInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Ottiene il nome, dimensioni delle righe, numero di righe, numero di colonne e l'indice della colonna chiave della tabella in corrispondenza dell'indice di tabella specificata.|  
|[Metodo GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Ottiene la stringa a livello di codice in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.|  
|[Metodo GetUserStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap delle stringhe utente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
