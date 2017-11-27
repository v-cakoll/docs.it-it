---
title: Metodo ISymUnmanagedBinder3::GetReaderFromCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder3.GetReaderFromCallback
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5e748742c1c67df0b33818e3f6f3c5786e07c65f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>Metodo ISymUnmanagedBinder3::GetReaderFromCallback
Consente di implementare o fornire mediante callback un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni di directory debug dalla memoria.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `importer`  
 [in] Un puntatore all'interfaccia di importazione dei metadati.  
  
 `fileName`  
 [in] Puntatore al nome del file.  
  
 `searchPath`  
 [in] Puntatore al percorso di ricerca.  
  
 `searchPolicy`  
 [in] Il valore di [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumerazione che specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.  
  
 `callback`  
 [in] Puntatore alla funzione di callback.  
  
 `pRetVal`  
 [out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedBinder3 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
