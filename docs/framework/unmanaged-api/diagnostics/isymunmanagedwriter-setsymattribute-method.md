---
title: Metodo ISymUnmanagedWriter::SetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab637b33797ebc5b6d16873cb460c465405b6849
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645652"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>Metodo ISymUnmanagedWriter::SetSymAttribute
Definisce un attributo personalizzato in base al relativo nome. Questi attributi sono contenuti nell'archivio simboli, a differenza degli attributi personalizzati di metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `parent`  
 [in] Il token di metadati per il quale viene definito l'attributo.  
  
 `name`  
 [in] Un puntatore a un `WCHAR` che contiene il nome dell'attributo.  
  
 `cData`  
 [in] Oggetto `ULONG32` che indica le dimensioni del `data` matrice.  
  
 `data`  
 [in] Il valore dell'attributo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
