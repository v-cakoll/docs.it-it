---
title: Metodo ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e283bea2ce2f4b2e17da6e8dcb85165d3c4d6693
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776969"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>Metodo ISymUnmanagedReader::GetMethodsFromDocumentPosition
Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `document`  
 [in] Il documento specificato.  
  
 `line`  
 [in] La riga del documento specificato.  
  
 `column`  
 [in] La colonna del documento specificato.  
  
 `cMethod`  
 [in] Dimensione della matrice `pRetVal`.  
  
 `pcMethod`  
 [out] Un puntatore a una variabile che riceve il numero di elementi restituiti nella `pRetVal` matrice.  
  
 `pRetVal`  
 [out] Una matrice di puntatori, ognuno dei quali punta a un [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) oggetto che rappresenta un metodo che contiene il punto di interruzione.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
