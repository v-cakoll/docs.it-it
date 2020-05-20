---
title: Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 82b46ea315009b65254735d44e355154b83b22e2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609495"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a>Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
Aprire una sezione di dati personalizzata speciale per creare informazioni sul mapping di intervalli da token a origine in. L'apertura di questa sezione quando un metodo è già aperto o viceversa è un errore.  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce `HRESULT`.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter5](isymunmanagedwriter5-interface.md)
