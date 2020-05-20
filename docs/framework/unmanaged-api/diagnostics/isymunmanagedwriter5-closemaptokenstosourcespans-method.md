---
title: Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: 053727604c795bf43a9b1658d5841fe85f53090a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614630"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a>Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
Chiudere la sezione relativa ai dati personalizzati speciali per informazioni sul mapping di intervalli da token a origine. Al termine della chiusura, non è possibile aggiungere altre informazioni sul mapping.  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce `HRESULT`.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter5](isymunmanagedwriter5-interface.md)
