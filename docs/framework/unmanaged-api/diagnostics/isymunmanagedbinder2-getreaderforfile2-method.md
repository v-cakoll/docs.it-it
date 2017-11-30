---
title: Metodo ISymUnmanagedBinder2::GetReaderForFile2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2.GetReaderForFile2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d232bfed801a17e1ee47dee7643ae0bf21d338e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="remarks"></a>Note  
 Questa versione del metodo possibile cercare il file PDB in aree diverse da subito dopo il modulo. I criteri della ricerca possono essere controllati combinando [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md). Ad esempio, `AllowReferencePathAccess | AllowSymbolServerAccess` Cerca il file PDB accanto al file eseguibile e su un server di simboli, ma non eseguire una query del Registro di sistema o utilizzare il percorso del file eseguibile. Se il `searchPath` parametro viene specificato, verranno cercate sempre tali directory.  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedBinder2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [GetReaderForFile (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
