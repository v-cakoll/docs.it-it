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
ms.openlocfilehash: 6e9ab623d5fe9fcfda2305df078e988a561afdc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427971"
---
# <a name="isymunmanagedwriterinitialize-method"></a>Metodo ISymUnmanagedWriter::Initialize
Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato e imposta il nome del file di output in cui verranno scritti i simboli di debug.  
  
 Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di qualsiasi altro metodo del writer. Alcuni writer possono richiedere un nome file. Tuttavia, è sempre possibile passare un nome file a questo metodo senza alcun effetto negativo sui writer che non utilizzano il nome file.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a>Parametri  
 `emitter`  
 in Puntatore all'interfaccia di emissione dei metadati.  
  
 `filename`  
 in Nome file in cui vengono scritti i simboli di debug. Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.  
  
 `pIStream`  
 in Se specificato, il writer di simboli emetterà i simboli nella <xref:System.Runtime.InteropServices.ComTypes.IStream> specificata anziché nel file specificato nel parametro `filename`. Il parametro `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` se si tratta di una ricompilazione completa; `false` se si tratta di una compilazione incrementale.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Metodo Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
