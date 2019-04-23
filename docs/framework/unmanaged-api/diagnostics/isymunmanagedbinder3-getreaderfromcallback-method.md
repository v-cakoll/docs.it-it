---
title: Metodo ISymUnmanagedBinder3::GetReaderFromCallback
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9487cf89d87b5f373302dc49a08c4fabb719e746
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160771"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>Metodo ISymUnmanagedBinder3::GetReaderFromCallback
Consente di implementare o fornire mediante callback un' `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni di directory di debug dalla memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Parametri  
 `importer`  
 [in] Un puntatore all'interfaccia di importazione dei metadati.  
  
 `fileName`  
 [in] Puntatore al nome del file.  
  
 `searchPath`  
 [in] Puntatore al percorso di ricerca.  
  
 `searchPolicy`  
 [in] Valore di [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumerazione che specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.  
  
 `callback`  
 [in] Puntatore alla funzione di callback.  
  
 `pRetVal`  
 [out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedBinder3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
