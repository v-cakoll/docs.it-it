---
title: Metodo ISymUnmanagedWriter::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 417cf623948d16147f9a1242d714f4df1311a314
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700943"
---
# <a name="isymunmanagedwriterinitialize-method"></a>Metodo ISymUnmanagedWriter::Initialize
Imposta l'interfaccia di emissione dei metadati con il quale verrà associato questo writer e imposta il nome del file di output in cui verranno scritti i simboli di debug.  
  
 Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di qualsiasi altro metodo di scrittura. Per alcuni writer richiedano un nome di file. Tuttavia, è possibile passare sempre un nome di file a questo metodo senza alcun effetto negativo sul writer che non usano il nome del file.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a>Parametri  
 `emitter`  
 [in] Un puntatore all'interfaccia di emissione dei metadati.  
  
 `filename`  
 [in] Il nome di file in cui vengono scritti i simboli di debug. Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.  
  
 `pIStream`  
 [in] Se specificato, il writer di simboli genererà i simboli nel dato <xref:System.Runtime.InteropServices.ComTypes.IStream> invece che al file specificato nel `filename` parametro. Il parametro `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` se si tratta di una ricompilazione completa. `false` se si tratta di una compilazione incrementale.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Metodo Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
