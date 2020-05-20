---
title: Metodo ISymUnmanagedVariable::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: a3ec0af33f3f1201ce2f6b62291dfc67696fecab
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610444"
---
# <a name="isymunmanagedvariablegetsignature-method"></a>Metodo ISymUnmanagedVariable::GetSignature
Ottiene la firma di questa variabile.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `cSig`  
 in Lunghezza del buffer a cui punta il `sig` parametro.  
  
 `pcSig`  
 out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere la firma.  
  
 `sig`  
 out Buffer in cui è archiviata la firma.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedVariable](isymunmanagedvariable-interface.md)
