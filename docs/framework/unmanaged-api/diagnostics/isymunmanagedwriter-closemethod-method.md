---
title: Metodo ISymUnmanagedWriter::CloseMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: fdf24bb8533da7914128f9477987c427442383bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610119"
---
# <a name="isymunmanagedwriterclosemethod-method"></a>Metodo ISymUnmanagedWriter::CloseMethod
Chiude il metodo corrente. Una volta chiuso un metodo, non è possibile definire altri simboli al suo interno.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Metodo OpenMethod](isymunmanagedwriter-openmethod-method.md)
