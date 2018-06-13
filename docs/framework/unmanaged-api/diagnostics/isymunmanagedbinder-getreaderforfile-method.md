---
title: Metodo ISymUnmanagedBinder::GetReaderForFile
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4f896dcd78061284416468968ba5a9a5fbbda2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428540"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a>Metodo ISymUnmanagedBinder::GetReaderForFile
Dato un'interfaccia di metadati e un nome di file, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> Struttura che verrà letti i simboli di debug associati al modulo.  
  
 Questo metodo verrà aprire il file di programma (PDB) di database solo se si trova accanto al file eseguibile. È stato modificato per motivi di sicurezza. Se occorre una ricerca più completa per il file PDB, usare il [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a>Parametri  
 `importer`  
 [in] Un puntatore all'interfaccia di importazione dei metadati.  
  
 `fileName`  
 [in] Puntatore al nome del file.  
  
 `searchPath`  
 [in] Puntatore al percorso di ricerca.  
  
 `pRetVal`  
 [out] Un puntatore che viene impostato sull'oggetto restituito <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [Metodo GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
