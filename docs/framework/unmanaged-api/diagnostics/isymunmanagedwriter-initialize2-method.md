---
title: Metodo ISymUnmanagedWriter::Initialize2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71eeeefc594c450d5fb95ebae17e3c1316301278
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481378"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>Metodo ISymUnmanagedWriter::Initialize2
Imposta l'interfaccia di emissione dei metadati con il quale verrà associato questo writer e imposta il nome del file di output in cui verranno scritti i simboli di debug. Questo metodo consente inoltre di impostare la posizione finale del file di database (PDB) del programma.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>Parametri  
 `emitter`  
 [in] Un puntatore all'interfaccia di emissione dei metadati.  
  
 `tempfilename`  
 [in] Un puntatore a un `WCHAR` che contiene il nome del file in cui vengono scritti i simboli di debug. Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.  
  
 `pIStream`  
 [in] Se specificato, il writer di simboli genera i simboli nel dato <xref:System.Runtime.InteropServices.ComTypes.IStream> invece che al file specificato nel `filename` parametro. Il parametro `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` se si tratta di una ricompilazione completa. `false` se si tratta di una compilazione incrementale.  
  
 `finalfilename`  
 [in] Un puntatore a un `WCHAR` vale a dire la stringa del percorso per la posizione finale del file PDB.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Metodo Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
