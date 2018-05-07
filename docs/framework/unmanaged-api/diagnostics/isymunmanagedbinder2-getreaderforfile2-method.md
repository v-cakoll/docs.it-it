---
title: Metodo ISymUnmanagedBinder2::GetReaderForFile2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cea8a322fab6ef76873e668c622ac63e3a3f2862
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>Metodo ISymUnmanagedBinder2::GetReaderForFile2
Dato un'interfaccia di metadati e un nome di file, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia che verrà letti i simboli di debug associati al modulo.  
  
 Questo metodo esegue una ricerca più completa per il file di programma (PDB) di database più di [ISymUnmanagedBinder::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
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
  
 `pRetVal`  
 [out] Un puntatore che viene impostato sull'oggetto restituito <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="remarks"></a>Note  
 Questa versione del metodo possibile cercare il file PDB in aree diverse da subito dopo il modulo. I criteri della ricerca possono essere controllati combinando [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md). Ad esempio, `AllowReferencePathAccess | AllowSymbolServerAccess` Cerca il file PDB accanto al file eseguibile e su un server di simboli, ma non eseguire una query del Registro di sistema o utilizzare il percorso del file eseguibile. Se il `searchPath` parametro viene specificato, verranno cercate sempre tali directory.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [Metodo GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
