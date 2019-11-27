---
title: Interfaccia ISymUnmanagedReader
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: 7ae978f5d2c9f7e90f4549c15a3935b441eabf04
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434004"
---
# <a name="isymunmanagedreader-interface"></a>Interfaccia ISymUnmanagedReader
Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|description|  
|------------|-----------------|  
|[Metodo GetDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Trova un documento.|  
|[Metodo GetDocuments](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Restituisce una matrice di tutti i documenti definiti nell'archivio simboli.|  
|[Metodo GetDocumentVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Ottiene la versione specificata del documento specificato.|  
|[Metodo GetGlobalVariables](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Restituisce tutte le variabili globali.|  
|[Metodo GetMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Ottiene un metodo del lettore di simboli, dato un token di metodo.|  
|[Metodo GetMethodByVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Ottiene un metodo del lettore di simboli, dato un token del metodo e un numero di versione di modifica e copia.|  
|[Metodo GetMethodFromDocumentPosition](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Restituisce il metodo che contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.|  
|[Metodo GetMethodsFromDocumentPosition](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione nella posizione specificata in un documento.|  
|[Metodo GetMethodVersion](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Ottiene la versione del metodo.|  
|[Metodo GetNamespaces](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Ottiene gli spazi dei nomi definiti in ambito globale all'interno dell'archivio simboli.|  
|[Metodo GetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Ottiene un attributo personalizzato in base al nome.|  
|[Metodo GetSymbolStoreFileName](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Fornisce il nome file su disco dell'archivio dei simboli.|  
|[Metodo GetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Restituisce il metodo specificato come punto di ingresso utente per il modulo, se disponibile.|  
|[Metodo GetVariables](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Restituisce una variabile non locale, data l'elemento padre e il nome.|  
|[Metodo Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati a cui verrà associato questo Reader, insieme al nome file del modulo.|  
|[Metodo ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.|  
|[Metodo UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
