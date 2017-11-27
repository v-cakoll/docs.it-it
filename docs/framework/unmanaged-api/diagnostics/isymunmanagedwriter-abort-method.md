---
title: Metodo ISymUnmanagedWriter::Abort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Abort
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29dd11972e8db80f36820bba1eb679070d02146e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterabort-method"></a>Metodo ISymUnmanagedWriter::Abort
Chiude il writer di simboli senza eseguire il commit i simboli per l'archivio dei simboli. Dopo questa chiamata, il writer di simboli diventa non valido per ulteriori aggiornamenti. Per eseguire il commit i simboli e chiudere il writer di simboli, utilizzare il [ISymUnmanagedWriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
