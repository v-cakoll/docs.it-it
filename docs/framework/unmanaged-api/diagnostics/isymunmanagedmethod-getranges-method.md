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
ms.openlocfilehash: 1f1bd9c33f24847eae4ff7d26c5b996cd34afb72
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448933"
---
# <a name="isymunmanagedmethodgetranges-method"></a>Metodo ISymUnmanagedMethod::GetRanges
Data una posizione in un documento, restituisce una matrice di coppie di offset di inizio e di fine che corrispondono agli intervalli di MSIL (Microsoft Intermediate Language) che la posizione copre all'interno di questo metodo. La matrice è una matrice di numeri interi e ha il formato [inizio, fine, inizio, fine]. Il numero di coppie di intervalli è la lunghezza della matrice divisa per 2.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `document`  
 in Documento per cui è richiesto l'offset.  
  
 `line`  
 in Riga del documento corrispondente agli intervalli.  
  
 `column`  
 in Colonna del documento corrispondente agli intervalli.  
  
 `cRanges`  
 [in] Dimensione della matrice `ranges`.  
  
 `pcRanges`  
 out Puntatore a un `ULONG32` che riceve la dimensione del buffer necessario per contenere gli intervalli.  
  
 `ranges`  
 out Puntatore al buffer che riceve gli intervalli.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
