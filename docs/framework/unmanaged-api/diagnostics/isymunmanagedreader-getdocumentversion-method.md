---
title: Metodo ISymUnmanagedReader::GetDocumentVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: c2cc541b2a78f16d5ca6b19405794faa825a9d72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615033"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>Metodo ISymUnmanagedReader::GetDocumentVersion
Ottiene la versione specificata del documento specificato. La versione del documento inizia con 1 e viene incrementata ogni volta che il documento viene aggiornato con il metodo [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) . Se il `pbCurrent` parametro è `true` , questa è la versione più recente del documento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a>Parametri  
 `pDoc`  
 in Documento specificato.  
  
 `version`  
 out Puntatore a una variabile che riceve la versione del documento specificato.  
  
 `pbCurrent`  
 out Puntatore a una variabile che riceve `true` se è la versione più recente del documento o se non è `false` la versione più recente.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](isymunmanagedreader-interface.md)
