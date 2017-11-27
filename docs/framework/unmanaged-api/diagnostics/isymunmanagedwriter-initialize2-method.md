---
title: Metodo ISymUnmanagedWriter::Initialize2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e76543c35a717b95ae37985648986abaf16bf85d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize2-method"></a>Metodo ISymUnmanagedWriter::Initialize2
Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer e il nome del file di output in cui verranno scritti i simboli di debug. Questo metodo consente inoltre di impostare la posizione finale del file di database (PDB) del programma.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
#### <a name="parameters"></a>Parametri  
 `emitter`  
 [in] Puntatore a interfaccia di emissione dei metadati.  
  
 `tempfilename`  
 [in] Un puntatore a un `WCHAR` che contiene il nome del file in cui vengono scritti i simboli di debug. Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.  
  
 `pIStream`  
 [in] Se specificato, il writer di simboli genererà i simboli nel determinato <xref:System.Runtime.InteropServices.ComTypes.IStream> anziché nel file specificato nella `filename` parametro. Il parametro `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` se si tratta di una ricompilazione completa. `false` se si tratta di una compilazione incrementale.  
  
 `finalfilename`  
 [in] Un puntatore a un `WCHAR` che rappresenta la stringa del percorso per la posizione finale del file PDB.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Initialize (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
