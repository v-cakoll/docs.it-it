---
title: Metodo ISymUnmanagedWriter2::DefineLocalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614695"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>Metodo ISymUnmanagedWriter2::DefineLocalVariable2
Definisce una singola variabile nell'ambito lessicale corrente. Questo metodo può essere chiamato più volte per una variabile con lo stesso nome che dispone di più case in un ambito. In questo caso, tuttavia, i valori dei `startOffset` parametri e `endOffset` non devono sovrapporsi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Parametri  
 `name`  
 in Nome della variabile locale.  
  
 `attributes`  
 in Attributi della variabile locale.  
  
 `sigToken`  
 in Token di metadati della firma.  
  
 `addrKind`  
 in Tipo di indirizzo.  
  
 `addr1`  
 in Primo indirizzo per la specifica del parametro.  
  
 `addr2`  
 in Secondo indirizzo per la specifica del parametro.  
  
 `addr3`  
 in Terzo indirizzo per la specifica del parametro.  
  
 `startOffset`  
 in Offset iniziale della variabile. Questo parametro è facoltativo. Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito. Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.  
  
 `endOffset`  
 in Offset finale della variabile. Questo parametro è facoltativo. Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito. Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
- [Metodo DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)
