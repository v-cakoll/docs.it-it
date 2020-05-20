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
ms.openlocfilehash: 97b9fa537fdd9147d6d9eda036013add5393e33c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441708"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>Metodo ISymUnmanagedBinder2::GetReaderForFile2
Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.  
  
 Questo metodo fornisce una ricerca più completa del file del database di programma (PDB) rispetto al metodo [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) .  
  
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
 in Valore dell'enumerazione [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) che specifica i criteri da utilizzare durante la ricerca di un lettore di simboli.  
  
 `pRetVal`  
 out Puntatore impostato sull'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) restituita.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="remarks"></a>Osservazioni  
 Questa versione del metodo può cercare il file PDB in aree diverse da destra accanto al modulo. I criteri di ricerca possono essere controllati combinando [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md). Ad esempio, `AllowReferencePathAccess | AllowSymbolServerAccess` Cerca il PDB accanto al file eseguibile e in un server di simboli, ma non esegue una query sul Registro di sistema o usa il percorso nel file eseguibile. Se `searchPath` viene specificato il parametro, verrà sempre eseguita la ricerca di tali directory.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedBinder2](isymunmanagedbinder2-interface.md)
- [Metodo GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md)
