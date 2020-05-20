---
title: Metodo ISymUnmanagedWriter2::DefineGlobalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: ed3c841c34b71b30f740117899353aa289e478d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614708"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a>Metodo ISymUnmanagedWriter2::DefineGlobalVariable2
Definisce una variabile globale singola.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parametri  
 `name`  
 in Nome della variabile globale.  
  
 `attributes`  
 in Attributi della variabile globale.  
  
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
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
- [Metodo DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)
