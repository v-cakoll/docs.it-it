---
title: Interfaccia ISymUnmanagedReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader
helpviewer_keywords: ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56e0012ae1412c0fb5b434d3b4c0221831296c60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader-interface"></a>Interfaccia ISymUnmanagedReader
Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio dei simboli.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetDocument (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Trova un documento.|  
|[GetDocuments (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Restituisce una matrice di tutti i documenti definiti nell'archivio simboli.|  
|[GetDocumentVersion (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Ottiene la versione specificata del documento specificato.|  
|[GetGlobalVariables (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Restituisce tutte le variabili globali.|  
|[GetMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Ottiene un metodo del lettore di simboli, dato un token di metodo.|  
|[GetMethodByVersion (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Ottiene un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e copia.|  
|[GetMethodFromDocumentPosition (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Restituisce il metodo che contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.|  
|[GetMethodsFromDocumentPosition (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.|  
|[GetMethodVersion (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Ottiene la versione del metodo.|  
|[GetNamespaces (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Ottiene gli spazi dei nomi definiti in ambito globale all'interno dell'archivio simboli.|  
|[GetSymAttribute (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Ottiene un attributo personalizzato in base al relativo nome.|  
|[GetSymbolStoreFileName (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Fornisce il nome di file su disco dell'archivio di simboli.|  
|[GetUserEntryPoint (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Restituisce il metodo che è stato specificato come punto di ingresso utente per il modulo, se presente.|  
|[GetVariables (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Restituisce una variabile non locale, padre e al nome.|  
|[Initialize (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che il lettore verrà associato, insieme al nome file del modulo.|  
|[ReplaceSymbolStore (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.|  
|[UpdateSymbolStore (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedReader2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
