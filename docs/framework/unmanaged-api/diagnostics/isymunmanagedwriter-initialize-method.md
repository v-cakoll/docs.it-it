---
title: Metodo ISymUnmanagedWriter::Initialize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bae368919941e6a0b234736f789320b62405a17b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize-method"></a>Metodo ISymUnmanagedWriter::Initialize
Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer e il nome del file di output in cui verranno scritti i simboli di debug.  
  
 Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di altri metodi di scrittura. Per alcuni writer possono richiedere un nome di file. Tuttavia, è possibile passare sempre un nome di file a questo metodo senza effetti negativi sui writer che non utilizzano il nome del file.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a>Parametri  
 `emitter`  
 [in] Puntatore a interfaccia di emissione dei metadati.  
  
 `filename`  
 [in] Il nome di file in cui vengono scritti i simboli di debug. Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.  
  
 `pIStream`  
 [in] Se specificato, il writer di simboli genererà i simboli nel determinato <xref:System.Runtime.InteropServices.ComTypes.IStream> anziché nel file specificato nella `filename` parametro. Il parametro `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` se si tratta di una ricompilazione completa. `false` se si tratta di una compilazione incrementale.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Initialize2 (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
