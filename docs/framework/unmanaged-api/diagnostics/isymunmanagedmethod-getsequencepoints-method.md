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
ms.openlocfilehash: c9a35f35d7aea34c0ef08c30415fde75fe71e645
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426050"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>Metodo ISymUnmanagedMethod::GetSequencePoints
Ottiene tutti i punti di sequenza all'interno del metodo.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `cPoints`  
 [in] Oggetto `ULONG32` che riceve le dimensioni del `offsets`, `documents`, `lines`, `columns`, `endLines`, e `endColumns` matrici.  
  
 `pcPoints`  
 [out] Un puntatore a un `ULONG32` che riceve la lunghezza del buffer necessaria per contenere i punti di sequenza.  
  
 `offsets`  
 [in] Matrice in cui archiviare il Microsoft intermedio language (MSIL) viene eseguito l'offset dall'inizio del metodo per i punti di sequenza.  
  
 `documents`  
 [in] Matrice in cui archiviare i documenti in cui si trovano i punti di sequenza.  
  
 `lines`  
 [in] Matrice in cui archiviare le righe dei documenti in cui sono posizionati i punti di sequenza.  
  
 `columns`  
 [in] Matrice in cui archiviare le colonne dei documenti in cui sono posizionati i punti di sequenza.  
  
 `endLines`  
 [in] Matrice di righe dei documenti in cui terminano i punti di sequenza.  
  
 `endColumns`  
 [in] Matrice di colonne dei documenti in cui terminano i punti di sequenza.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
