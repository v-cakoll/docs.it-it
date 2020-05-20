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
ms.openlocfilehash: aba551a1973a41a909869316cda07e8d655e9882
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614838"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>Metodo ISymUnmanagedWriter::DefineField
Definisce una singola variabile che non si trova all'interno di un metodo. Questo metodo viene utilizzato per determinati campi in classi, campi di bit e così via.  
  
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
 in Il tipo di metadati o il token del metodo.  
  
 `name`  
 in Nome del campo.  
  
 `attributes`  
 in Attributi del campo.  
  
 `cSig`  
 in Oggetto `ULONG32` che rappresenta la dimensione, in caratteri, del buffer necessario per contenere la firma del campo.  
  
 `signature`  
 in Matrice delle firme dei campi.  
  
 `addrKind`  
 in Tipo di indirizzo.  
  
 `addr1`  
 in Primo indirizzo per la specifica del campo.  
  
 `addr2`  
 in Secondo indirizzo per la specifica del campo.  
  
 `addr3`  
 in Terzo indirizzo per la specifica del campo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
