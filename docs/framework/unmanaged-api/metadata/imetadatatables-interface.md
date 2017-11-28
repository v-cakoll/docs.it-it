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
ms.openlocfilehash: c89d615fbeeff4a60eb386d58c573ee7905f538d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables-interface"></a>Interfaccia IMetaDataTables
Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetBlob (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Ottiene un puntatore per l'oggetto binario di grandi dimensioni (BLOB) in corrispondenza dell'indice della colonna specificata.|  
|[GetBlobHeapSize (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap BLOB.|  
|[GetCodedTokenInfo (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Ottiene un puntatore a una matrice di token associato all'indice di riga specificato.|  
|[GetColumn (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Ottiene un puntatore ai valori contenuti nella colonna in corrispondenza dell'indice di colonna specificata, nella tabella in corrispondenza dell'indice di tabella specificata.|  
|[GetColumnInfo (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Ottiene i dati relativi alla colonna specificata nella tabella specificata.|  
|[GetGuid (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Ottiene un GUID della riga in corrispondenza dell'indice specificato.|  
|[GetGuidHeapSize (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap dei GUID.|  
|[GetNextBlob (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Ottiene l'indice del successivo BLOB nella tabella.|  
|[GetNextGuid (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Ottiene l'indice del successivo valore GUID nella colonna della tabella corrente.|  
|[GetNextString (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Ottiene l'indice della stringa successiva nella colonna della tabella corrente.|  
|[GetNextUserString (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Ottiene l'indice della riga che contiene la stringa hardcoded successiva nella colonna della tabella corrente.|  
|[GetNumTables (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Ottiene il numero di tabelle nell'ambito dell'oggetto corrente `IMetaDataTables` istanza.|  
|[GetRow (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Ottiene la riga in corrispondenza dell'indice di riga specificata, nella tabella in corrispondenza dell'indice di tabella specificata.|  
|[GetString (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Ottiene la stringa in corrispondenza dell'indice specificato dalla colonna della tabella nell'ambito di riferimento corrente.|  
|[GetStringHeapSize (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap delle stringhe.|  
|[GetTableIndex (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Ottiene l'indice per la tabella a cui fa riferimento il token specificato.|  
|[GetTableInfo (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Ottiene il nome, dimensioni delle righe, numero di righe, numero di colonne e l'indice della colonna chiave della tabella in corrispondenza dell'indice di tabella specificata.|  
|[GetUserString (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Ottiene la stringa a livello di codice in corrispondenza dell'indice specificato nella colonna stringa nell'ambito corrente.|  
|[GetUserStringHeapSize (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Ottiene le dimensioni, in byte, dell'heap delle stringhe utente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataTables2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
