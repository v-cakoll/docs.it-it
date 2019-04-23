---
title: Metodo ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 979d14b4c404c3bf12c427bd5b8b1d4997805e7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160680"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>Metodo ISymUnmanagedWriter::RemapToken
Notifica il writer di simboli che ha è stato modificato il mapping di un token di metadati come il costo veniva calcolato i metadati. Se il writer di simboli è archiviato il token precedente nell'archivio dei simboli, è necessario aggiornare che il token archiviato con il nuovo valore oppure salvare la mappa per il lettore di simboli corrispondenti modificare il mapping durante la fase di lettura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>Parametri  
 `oldToken`  
 [in] Il token di metadati che è stato rimappato.  
  
 `newToken`  
 [in] Il nuovo token di metadati a cui `oldToken` è stata rimappata.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
