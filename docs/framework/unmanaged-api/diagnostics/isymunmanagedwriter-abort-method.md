---
title: Metodo ISymUnmanagedWriter::Abort
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610158"
---
# <a name="isymunmanagedwriterabort-method"></a>Metodo ISymUnmanagedWriter::Abort
Chiude il writer di simboli senza eseguire il commit dei simboli nell'archivio dei simboli. Dopo questa chiamata, il writer di simboli diventa non valido per ulteriori aggiornamenti. Per eseguire il commit dei simboli e chiudere il writer di simboli, usare invece il metodo [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
