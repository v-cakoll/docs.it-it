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
ms.openlocfilehash: 1553e616f60b4f05c06b6457d47454dfb4bc2eb7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614773"
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
 in Se specificato, il writer di simboli emetterà i simboli nell'oggetto specificato <xref:System.Runtime.InteropServices.ComTypes.IStream> anziché nel file specificato nel `filename` parametro. `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` Se si tratta di una ricompilazione completa; `false`se si tratta di una compilazione incrementale.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Metodo Initialize2](isymunmanagedwriter-initialize2-method.md)
