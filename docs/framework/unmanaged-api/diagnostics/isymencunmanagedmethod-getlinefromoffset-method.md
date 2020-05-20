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
ms.openlocfilehash: d9a7b18e90a3038c1ffb634ccc7315143875c809
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441916"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>Metodo ISymENCUnmanagedMethod::GetLineFromOffset
Ottiene le informazioni sulla riga associate a un offset. Se il parametro offset ( `dwOffset` ) non è un punto di sequenza, questo metodo ottiene le informazioni sulla riga associate all'offset precedente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Oggetto `ULONG32` che contiene l'offset.  
  
 `pline`  
 out Puntatore a un oggetto `ULONG32` che riceve la riga.  
  
 `pcolumn`  
 out Puntatore a un oggetto `ULONG32` che riceve la colonna.  
  
 `pendLine`  
 out Puntatore a un oggetto `ULONG32` che riceve la riga finale.  
  
 `pendColumn`  
 out Puntatore a un oggetto `ULONG32` che riceve la colonna finale.  
  
 `pdwStartOffset`  
 out Puntatore a un oggetto `ULONG32` che riceve il punto di sequenza associato.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
