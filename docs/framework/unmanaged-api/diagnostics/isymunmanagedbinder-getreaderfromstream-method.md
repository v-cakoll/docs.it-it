---
title: Metodo ISymUnmanagedBinder::GetReaderFromStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderFromStream
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aa6a2e60e34f6c3a78343318ae102883da84e266
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a>Metodo ISymUnmanagedBinder::GetReaderFromStream
Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) simboli di struttura che verrà letto il debug dall'archivio di simboli specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a>Parametri  
 `importer`  
 [in] Un puntatore all'interfaccia di importazione dei metadati.  
  
 `pstream`  
 [in] Puntatore al flusso che contiene l'archivio dei simboli.  
  
 `pRetVal`  
 [out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaccia.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
