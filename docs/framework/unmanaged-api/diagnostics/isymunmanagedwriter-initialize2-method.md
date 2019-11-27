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
ms.openlocfilehash: 041df959139a0be77f40d6aa5655ff15f93fb26f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427951"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>Metodo ISymUnmanagedWriter::Initialize2
Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato e imposta il nome del file di output in cui verranno scritti i simboli di debug. Questo metodo consente inoltre di impostare il percorso finale del file del database di programma (PDB).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>Parametri  
 `emitter`  
 in Puntatore all'interfaccia di emissione dei metadati.  
  
 `tempfilename`  
 in Puntatore a un `WCHAR` che contiene il nome file in cui vengono scritti i simboli di debug. Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.  
  
 `pIStream`  
 in Se specificato, il writer di simboli emette i simboli nella <xref:System.Runtime.InteropServices.ComTypes.IStream> specificata anziché nel file specificato nel parametro `filename`. Il parametro `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` se si tratta di una ricompilazione completa; `false` se si tratta di una compilazione incrementale.  
  
 `finalfilename`  
 in Puntatore a un `WCHAR` che rappresenta la stringa di percorso alla posizione finale del file PDB.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Metodo Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
