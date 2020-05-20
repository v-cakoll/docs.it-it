---
title: Metodo ISymUnmanagedWriter::Close
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 0a7ecd475a8031fedb2c8474593b45045fcc6fb9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610132"
---
# <a name="isymunmanagedwriterclose-method"></a>Metodo ISymUnmanagedWriter::Close
Chiude il writer di simboli dopo aver eseguito il commit dei simboli nell'archivio dei simboli.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Osservazioni  
 Dopo questa chiamata, il writer di simboli diventa non valido per ulteriori aggiornamenti. Per chiudere il writer di simboli senza eseguire il commit dei simboli, usare invece il metodo [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
