---
title: Metodo ISymUnmanagedReader::GetDocument
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7fcc18b1441093a3e3a1a0e813ccfb4ba3ad507b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetdocument-method"></a>Metodo ISymUnmanagedReader::GetDocument
Trova un documento. Il linguaggio del documento, fornitore e tipo sono facoltativi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
#### <a name="parameters"></a>Parametri  
 `url`  
 [in] L'URL che identifica il documento.  
  
 `language`  
 [in] Il linguaggio del documento. Questo parametro è facoltativo.  
  
 `languageVendor`  
 [in] L'identità del fornitore del linguaggio del documento. Questo parametro è facoltativo.  
  
 `documentType`  
 [in] Il tipo del documento. Questo parametro è facoltativo.  
  
 `pRetVal`  
 [out] Puntatore a interfaccia restituito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedReader (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
