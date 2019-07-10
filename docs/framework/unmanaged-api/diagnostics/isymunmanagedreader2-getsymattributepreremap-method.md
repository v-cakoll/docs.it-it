---
title: Metodo ISymUnmanagedReader2::GetSymAttributePreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46c608a644619c28709de135d7c062175b012d80
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777384"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>Metodo ISymUnmanagedReader2::GetSymAttributePreRemap
Ottiene un attributo personalizzato in base al relativo nome. A differenza dei metadati di attributi personalizzati, questi attributi sono contenuti nell'archivio simboli.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `parent`  
 [in] Il token di metadati dell'elemento padre.  
  
 `name`  
 [in] Un puntatore a un `WCHAR` che contiene il nome.  
  
 `cBuffer`  
 [in] Oggetto `ULONG32` che indica le dimensioni del `buffer` matrice.  
  
 `pcBuffer`  
 [out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere i byte di attributo.  
  
 `buffer`  
 [out] Puntatore al buffer che riceve i byte di attributo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
