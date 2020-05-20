---
title: Interfaccia ISymUnmanagedDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: a8ff6d3a925773e58e0713a87b167420c246f85b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615566"
---
# <a name="isymunmanageddocument-interface"></a>Interfaccia ISymUnmanagedDocument
Rappresenta un documento al quale fa riferimento un archivio di simboli. Un documento è definito da un URL (Uniform Resource Locator) e da un GUID del tipo di documento. È possibile individuare il documento indipendentemente dalla relativa modalità di archiviazione utilizzando l'URL e il GUID del tipo di documento. È possibile archiviare l'origine del documento nell'archivio dei simboli e recuperarla tramite questa interfaccia.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo FindClosestLine](isymunmanageddocument-findclosestline-method.md)|Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga del documento che può essere o meno un punto di sequenza.|  
|[Metodo GetCheckSum](isymunmanageddocument-getchecksum-method.md)|Ottiene il checksum.|  
|[Metodo GetCheckSumAlgorithmId](isymunmanageddocument-getchecksumalgorithmid-method.md)|Ottiene l'identificatore dell'algoritmo di checksum oppure restituisce un GUID di tutti gli zeri in assenza di checksum.|  
|[Metodo GetDocumentType](isymunmanageddocument-getdocumenttype-method.md)|Ottiene il tipo di documento di questo documento.|  
|[Metodo GetLanguage](isymunmanageddocument-getlanguage-method.md)|Ottiene l'identificatore di lingua di questo documento.|  
|[Metodo GetLanguageVendor](isymunmanageddocument-getlanguagevendor-method.md)|Ottiene il fornitore del linguaggio del documento.|  
|[Metodo GetSourceLength](isymunmanageddocument-getsourcelength-method.md)|Recupera la lunghezza, in byte, dell'origine incorporata.|  
|[Metodo GetSourceRange](isymunmanageddocument-getsourcerange-method.md)|Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato.|  
|[Metodo GetURL](isymunmanageddocument-geturl-method.md)|Restituisce l'URL per questo documento.|  
|[Metodo HasEmbeddedSource](isymunmanageddocument-hasembeddedsource-method.md)|Restituisce `true` se l'origine del documento è incorporata nei simboli di debug; in caso contrario, restituisce `false` .|  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
