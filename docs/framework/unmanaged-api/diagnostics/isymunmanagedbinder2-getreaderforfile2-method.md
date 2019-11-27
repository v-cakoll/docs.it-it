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
ms.openlocfilehash: 756ba2e71ca2e3e817a0a8b89165bb807368c1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449337"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>Metodo ISymUnmanagedBinder2::GetReaderForFile2
Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.  
  
 Questo metodo fornisce una ricerca più completa del file del database di programma (PDB) rispetto al metodo [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Parametri  
 `importer`  
 in Puntatore all'interfaccia di importazione dei metadati.  
  
 `fileName`  
 in Puntatore al nome del file.  
  
 `searchPath`  
 in Puntatore al percorso di ricerca.  
  
 `searchPolicy`  
 in Valore dell'enumerazione [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) che specifica i criteri da utilizzare durante la ricerca di un lettore di simboli.  
  
 `pRetVal`  
 out Puntatore impostato sull'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) restituita.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="remarks"></a>Osservazioni  
 Questa versione del metodo può cercare il file PDB in aree diverse da destra accanto al modulo. I criteri di ricerca possono essere controllati combinando [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md). `AllowReferencePathAccess | AllowSymbolServerAccess`, ad esempio, Cerca il PDB accanto al file eseguibile e in un server di simboli, ma non esegue una query sul Registro di sistema o usa il percorso nel file eseguibile. Se viene specificato il parametro `searchPath`, viene sempre eseguita la ricerca di tali directory.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [Metodo GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
