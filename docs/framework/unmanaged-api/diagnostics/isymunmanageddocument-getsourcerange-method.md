---
title: Metodo ISymUnmanagedDocument::GetSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: 841379702e24428a8092cfd1d2cbd3c5b4e17ba4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615605"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>Metodo ISymUnmanagedDocument::GetSourceRange
Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato. Il buffer deve essere sufficientemente grande da contenere l'origine.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `startLine`  
 in Riga iniziale del documento corrente.  
  
 `startColumn`  
 in Colonna iniziale del documento corrente.  
  
 `endLine`  
 in Riga finale del documento corrente.  
  
 `endColumn`  
 in Colonna finale del documento corrente.  
  
 `cSourceBytes`  
 in Dimensioni, in byte, dell'origine.  
  
 `pcSourceBytes`  
 out Puntatore a una variabile che riceve la dimensione di origine.  
  
 `source`  
 out La dimensione e la lunghezza dell'intervallo specificato, in byte, del documento di origine.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedDocument](isymunmanageddocument-interface.md)
