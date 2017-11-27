---
title: Interfaccia ISymUnmanagedDocument
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument
helpviewer_keywords: ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8654f28cc4d82a5ed1419215807ec3360522fd55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocument-interface"></a>Interfaccia ISymUnmanagedDocument
Rappresenta un documento al quale fa riferimento un archivio di simboli. Un documento viene definito da un uniform resource locator (URL) e un GUID del tipo di documento. È possibile individuare il documento indipendentemente dalla modalità di archiviazione utilizzando l'URL e il GUID di tipo di documento. È possibile archiviare l'origine del documento nell'archivio di simboli e recuperata mediante questa interfaccia.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[FindClosestLine (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga in questo documento che non può essere un punto di sequenza.|  
|[GetCheckSum (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|Ottiene il checksum.|  
|[GetCheckSumAlgorithmId (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|Ottiene l'identificatore dell'algoritmo di checksum o restituisce un GUID di tutti gli zeri, se non sono presenti checksum.|  
|[GetDocumentType (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|Ottiene il tipo di questo documento.|  
|[GetLanguage (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|Ottiene l'identificatore di lingua di questo documento.|  
|[GetLanguageVendor (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|Recupera il fornitore di linguaggio di questo documento.|  
|[GetSourceLength (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|Recupera la lunghezza, in byte, dell'origine incorporata.|  
|[GetSourceRange (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato.|  
|[Metodo GetURL](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|Restituisce l'URL per il documento.|  
|[HasEmbeddedSource (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|Restituisce `true` se il documento di origine è incorporata nei simboli di debug; in caso contrario, restituisce `false`.|  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
