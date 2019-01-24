---
title: Metodo ISymUnmanagedMethod::GetRanges
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6afe0f0d8780a93a7d98f24a11bb67ef65ebf63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604275"
---
# <a name="isymunmanagedmethodgetranges-method"></a>Metodo ISymUnmanagedMethod::GetRanges
Data una posizione in un documento, restituisce una matrice di coppie di offset iniziale e finale che corrispondono agli intervalli di Microsoft intermediate language (MSIL) che la posizione all'interno del metodo. La matrice è una matrice di interi e ha il formato [inizio, fine, inizio, fine]. Il numero di coppie di intervallo è la lunghezza della matrice divisa per 2.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `document`  
 [in] Il documento per cui è richiesto l'offset.  
  
 `line`  
 [in] Riga del documento corrispondente agli intervalli.  
  
 `column`  
 [in] Colonna del documento corrispondente agli intervalli.  
  
 `cRanges`  
 [in] Dimensione della matrice `ranges`.  
  
 `pcRanges`  
 [out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere gli intervalli.  
  
 `ranges`  
 [out] Puntatore al buffer che riceve gli intervalli.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
