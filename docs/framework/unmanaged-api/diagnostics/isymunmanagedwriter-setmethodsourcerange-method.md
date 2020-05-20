---
title: Metodo ISymUnmanagedWriter::SetMethodSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: 4ba3f31ae6d6b67d7beaa2f709bf6174b721136d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609521"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>Metodo ISymUnmanagedWriter::SetMethodSourceRange
Specifica l'inizio e la fine effettivi di un metodo in un file di origine. Utilizzare questo metodo per specificare l'ambito di un metodo indipendentemente dai punti di sequenza presenti all'interno del metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a>Parametri  
 `startDoc`  
 in Puntatore al documento che contiene la posizione iniziale.  
  
 `startLine`  
 in Numero di riga iniziale.  
  
 `startColumn`  
 in Colonna iniziale.  
  
 `endDoc`  
 in Puntatore al documento che contiene la posizione finale.  
  
 `endLine`  
 in Numero di riga finale.  
  
 `endColumn`  
 in Numero di colonna finale.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
