---
title: Metodo ISymUnmanagedMethod::GetSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad9e552d31944523222798fe7dba2201461b1243
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487257"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>Metodo ISymUnmanagedMethod::GetSequencePoints
Ottiene tutti i punti di sequenza all'interno di questo metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `cPoints`  
 [in] Oggetto `ULONG32` che riceve le dimensioni dei `offsets`, `documents`, `lines`, `columns`, `endLines`, e `endColumns` matrici.  
  
 `pcPoints`  
 [out] Un puntatore a un `ULONG32` che riceve la lunghezza del buffer necessaria per contenere i punti di sequenza.  
  
 `offsets`  
 [in] Matrice in cui archiviare il Microsoft intermedio language (MSIL) viene eseguito l'offset dall'inizio del metodo per i punti di sequenza.  
  
 `documents`  
 [in] Matrice in cui archiviare i documenti in cui sono posizionati i punti di sequenza.  
  
 `lines`  
 [in] Matrice in cui archiviare le righe dei documenti in cui sono posizionati i punti di sequenza.  
  
 `columns`  
 [in] Matrice in cui archiviare le colonne dei documenti in cui sono posizionati i punti di sequenza.  
  
 `endLines`  
 [in] Matrice di righe dei documenti in cui terminano i punti di sequenza.  
  
 `endColumns`  
 [in] Matrice di colonne dei documenti in cui terminano i punti di sequenza.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
