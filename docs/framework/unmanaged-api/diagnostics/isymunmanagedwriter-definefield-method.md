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
ms.openlocfilehash: 5d5b3c60845fce39ce7f904c6871e7feb16e8970
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterdefinefield-method"></a>Metodo ISymUnmanagedWriter::DefineField
Definisce una singola variabile che non è presente all'interno di un metodo. Questo metodo è usato per alcuni campi nelle classi, i campi di bit e così via.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `parent`  
 [in] Il tipo di metadati o il metodo token.  
  
 `name`  
 [in] Il nome del campo.  
  
 `attributes`  
 [in] Gli attributi di campo.  
  
 `cSig`  
 [in] Oggetto `ULONG32` che rappresenta la dimensione, in caratteri, del buffer necessaria per contenere la firma del campo.  
  
 `signature`  
 [in] Matrice di firme di campo.  
  
 `addrKind`  
 [in] Il tipo di indirizzo.  
  
 `addr1`  
 [in] Il primo indirizzo relativo al campo specificato.  
  
 `addr2`  
 [in] Il secondo indirizzo per la specifica del campo.  
  
 `addr3`  
 [in] Terzo indirizzo relativo al campo specificato.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
