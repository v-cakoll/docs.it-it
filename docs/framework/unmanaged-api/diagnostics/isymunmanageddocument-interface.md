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
ms.openlocfilehash: 3fa7b6b19d81e374cdb09b07ec181a7f4249a5eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449102"
---
# <a name="isymunmanageddocument-interface"></a>Interfaccia ISymUnmanagedDocument
Rappresenta un documento al quale fa riferimento un archivio di simboli. Un documento è definito da un URL (Uniform Resource Locator) e da un GUID del tipo di documento. È possibile individuare il documento indipendentemente dalla relativa modalità di archiviazione utilizzando l'URL e il GUID del tipo di documento. È possibile archiviare l'origine del documento nell'archivio dei simboli e recuperarla tramite questa interfaccia.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo FindClosestLine](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga del documento che può essere o meno un punto di sequenza.|  
|[Metodo GetCheckSum](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|Ottiene il checksum.|  
|[Metodo GetCheckSumAlgorithmId](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|Ottiene l'identificatore dell'algoritmo di checksum oppure restituisce un GUID di tutti gli zeri in assenza di checksum.|  
|[Metodo GetDocumentType](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|Ottiene il tipo di documento di questo documento.|  
|[Metodo GetLanguage](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|Ottiene l'identificatore di lingua di questo documento.|  
|[Metodo GetLanguageVendor](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|Ottiene il fornitore del linguaggio del documento.|  
|[Metodo GetSourceLength](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|Recupera la lunghezza, in byte, dell'origine incorporata.|  
|[Metodo GetSourceRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato.|  
|[Metodo GetURL](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|Restituisce l'URL per questo documento.|  
|[Metodo HasEmbeddedSource](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|Restituisce `true` se l'origine del documento è incorporata nei simboli di debug; in caso contrario, restituisce `false`.|  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
