---
title: Metodo ISymUnmanagedWriter::DefineField
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37794d40b4b379c5d3a05935cf1f2b7b3da11baa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777372"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>Metodo ISymUnmanagedWriter::DefineField
Definisce una singola variabile che non è incluso un metodo. Questo metodo è utilizzato per alcuni campi nelle classi, campi di bit e così via.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parametri  
 `parent`  
 [in] Il tipo di metadati o il metodo token.  
  
 `name`  
 [in] Il nome del campo.  
  
 `attributes`  
 [in] Gli attributi di campo.  
  
 `cSig`  
 [in] Oggetto `ULONG32` vale a dire le dimensioni, in caratteri, del buffer necessaria per contenere la firma del campo.  
  
 `signature`  
 [in] Matrice di firme di campo.  
  
 `addrKind`  
 [in] Il tipo di indirizzo.  
  
 `addr1`  
 [in] Il primo indirizzo relativo al campo specificato.  
  
 `addr2`  
 [in] Il secondo indirizzo relativo al campo specificato.  
  
 `addr3`  
 [in] Terzo indirizzo relativo al campo specificato.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
