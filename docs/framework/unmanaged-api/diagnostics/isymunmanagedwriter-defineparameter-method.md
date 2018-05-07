---
title: Metodo ISymUnmanagedWriter::DefineParameter
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6b01abc16334dbe091e7586efcce1c3e390a64e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>Metodo ISymUnmanagedWriter::DefineParameter
Definisce un singolo parametro nel metodo corrente. Il tipo di parametro viene ricavato dalla posizione del parametro (sequenza) all'interno della firma del metodo.  
  
 Se i parametri vengono definiti nei metadati per un determinato metodo, non è necessario definire nuovamente utilizzando questo metodo. I lettori di simbolo devono controllare i metadati normale per i parametri prima di verificare l'archivio dei simboli.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 [in] Il nome del parametro.  
  
 `attributes`  
 [in] Gli attributi di parametro.  
  
 `sequence`  
 [in] La firma di parametro.  
  
 `addrKind`  
 [in] Il tipo di indirizzo.  
  
 `addr1`  
 [in] Il primo indirizzo per la specifica del parametro.  
  
 `addr2`  
 [in] Il secondo indirizzo per la specifica del parametro.  
  
 `addr3`  
 [in] Terzo indirizzo per la specifica del parametro.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
