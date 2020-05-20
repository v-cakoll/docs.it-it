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
ms.openlocfilehash: c695aa80ea3bf90a29ce7c5d11eda7fae5fe7b2d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614812"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>Metodo ISymUnmanagedWriter::DefineParameter
Definisce un singolo parametro nel metodo corrente. Il tipo di parametro viene tratto dalla posizione (sequenza) del parametro all'interno della firma del metodo.  
  
 Se i parametri sono definiti nei metadati per un determinato metodo, non è necessario definirli nuovamente utilizzando questo metodo. I lettori di simboli devono controllare i metadati normali per i parametri prima di controllare l'archivio dei simboli.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parametri  
 `name`  
 in Nome del parametro.  
  
 `attributes`  
 in Attributi di parametro.  
  
 `sequence`  
 in Firma del parametro.  
  
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
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
