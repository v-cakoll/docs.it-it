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
ms.openlocfilehash: b372021fcda39d9973d96a9c39e93e38617887a6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615462"
---
# <a name="isymunmanagedreader-interface"></a>Interfaccia ISymUnmanagedReader
Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetDocument](isymunmanagedreader-getdocument-method.md)|Trova un documento.|  
|[Metodo GetDocuments](isymunmanagedreader-getdocuments-method.md)|Restituisce una matrice di tutti i documenti definiti nell'archivio simboli.|  
|[Metodo GetDocumentVersion](isymunmanagedreader-getdocumentversion-method.md)|Ottiene la versione specificata del documento specificato.|  
|[Metodo GetGlobalVariables](isymunmanagedreader-getglobalvariables-method.md)|Restituisce tutte le variabili globali.|  
|[Metodo GetMethod](isymunmanagedreader-getmethod-method.md)|Ottiene un metodo del lettore di simboli, dato un token di metodo.|  
|[Metodo GetMethodByVersion](isymunmanagedreader-getmethodbyversion-method.md)|Ottiene un metodo del lettore di simboli, dato un token del metodo e un numero di versione di modifica e copia.|  
|[Metodo GetMethodFromDocumentPosition](isymunmanagedreader-getmethodfromdocumentposition-method.md)|Restituisce il metodo che contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.|  
|[Metodo GetMethodsFromDocumentPosition](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione nella posizione specificata in un documento.|  
|[Metodo GetMethodVersion](isymunmanagedreader-getmethodversion-method.md)|Ottiene la versione del metodo.|  
|[Metodo GetNamespaces](isymunmanagedreader-getnamespaces-method.md)|Ottiene gli spazi dei nomi definiti in ambito globale all'interno dell'archivio simboli.|  
|[Metodo GetSymAttribute](isymunmanagedreader-getsymattribute-method.md)|Ottiene un attributo personalizzato in base al nome.|  
|[Metodo GetSymbolStoreFileName](isymunmanagedreader-getsymbolstorefilename-method.md)|Fornisce il nome file su disco dell'archivio dei simboli.|  
|[Metodo GetUserEntryPoint](isymunmanagedreader-getuserentrypoint-method.md)|Restituisce il metodo specificato come punto di ingresso utente per il modulo, se disponibile.|  
|[Metodo GetVariables](isymunmanagedreader-getvariables-method.md)|Restituisce una variabile non locale, data l'elemento padre e il nome.|  
|[Metodo Initialize](isymunmanagedreader-initialize-method.md)|Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati a cui verrà associato questo Reader, insieme al nome file del modulo.|  
|[Metodo ReplaceSymbolStore](isymunmanagedreader-replacesymbolstore-method.md)|Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.|  
|[Metodo UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md)|Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedReader2](isymunmanagedreader2-interface.md)
