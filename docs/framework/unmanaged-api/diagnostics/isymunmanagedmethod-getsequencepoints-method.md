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
ms.openlocfilehash: 451cfecde7e14fad9d3fed3367112e1fb59796e5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615144"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>Metodo ISymUnmanagedMethod::GetSequencePoints
Ottiene tutti i punti di sequenza all'interno di questo metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Oggetto `ULONG32` che riceve le dimensioni delle `offsets` matrici, `documents` , `lines` , `columns` , `endLines` e `endColumns` .  
  
 `pcPoints`  
 out Puntatore a un oggetto `ULONG32` che riceve la lunghezza del buffer necessaria per contenere i punti di sequenza.  
  
 `offsets`  
 in Matrice in cui archiviare gli offset MSIL (Microsoft Intermediate Language) dall'inizio del metodo per i punti di sequenza.  
  
 `documents`  
 in Matrice in cui archiviare i documenti in cui si trovano i punti di sequenza.  
  
 `lines`  
 in Matrice in cui archiviare le righe dei documenti in corrispondenza delle quali si trovano i punti di sequenza.  
  
 `columns`  
 in Matrice in cui archiviare le colonne dei documenti in cui si trovano i punti di sequenza.  
  
 `endLines`  
 in Matrice di righe nei documenti a cui terminano i punti di sequenza.  
  
 `endColumns`  
 in Matrice di colonne nei documenti a cui terminano i punti di sequenza.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
