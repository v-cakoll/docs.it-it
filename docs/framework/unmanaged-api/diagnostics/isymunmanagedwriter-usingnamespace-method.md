---
title: Metodo ISymUnmanagedWriter::UsingNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca9f3488c9fb2280d2ceb99c87a54d99c1a33b6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587726"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a>Metodo ISymUnmanagedWriter::UsingNamespace
Specifica il nome completo dello spazio dei nomi specificato viene utilizzato all'interno dell'ambito lessicale attualmente aperto. Verrà usato lo spazio dei nomi all'interno di tutti gli ambiti che ereditano dall'ambito attualmente aperto. La chiusura dell'ambito corrente anche interromperà l'utilizzo dello spazio dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fullName`  
 [in] Un puntatore al nome completo dello spazio dei nomi.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
