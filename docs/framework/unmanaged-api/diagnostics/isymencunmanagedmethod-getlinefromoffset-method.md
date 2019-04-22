---
title: Metodo ISymENCUnmanagedMethod::GetLineFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3106c6680750826306cffb31e599ee2260bf4ad7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136448"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>Metodo ISymENCUnmanagedMethod::GetLineFromOffset
Ottiene le informazioni della riga associate a un offset. Se il parametro offset (`dwOffset`) non è un punto di sequenza, questo metodo ottiene le informazioni della riga associate all'offset precedente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwOffset`  
 [in] Oggetto `ULONG32` che contiene l'offset.  
  
 `pline`  
 [out] Un puntatore a un `ULONG32` che riceve la riga.  
  
 `pcolumn`  
 [out] Un puntatore a un `ULONG32` che riceve la colonna.  
  
 `pendLine`  
 [out] Un puntatore a un `ULONG32` che riceve la riga finale.  
  
 `pendColumn`  
 [out] Un puntatore a un `ULONG32` che riceve la colonna finale.  
  
 `pdwStartOffset`  
 [out] Un puntatore a un `ULONG32` che riceve il punto di sequenza associata.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymENCUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
