---
title: Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 004e1ddae8a6c0262846422a2eeb4314a4c82f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121617"
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

- [Interfaccia ISymUnmanagedWriter5](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
