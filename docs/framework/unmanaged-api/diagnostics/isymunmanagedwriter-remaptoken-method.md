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
ms.openlocfilehash: 53cc908e0dc8cc5cc980ec365ccac0df4e620cac
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609768"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>Metodo ISymUnmanagedWriter::RemapToken
Notifica al writer di simboli che è stato eseguito il mapping di un token di metadati durante la creazione dei metadati. Se il writer di simboli ha archiviato il token precedente nell'archivio dei simboli, deve aggiornare il token archiviato con il nuovo valore oppure salvare la mappa affinché il lettore di simboli corrispondente venga rimappato durante la fase di lettura.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>Parametri  
 `oldToken`  
 in Token di metadati di cui è stato eseguito il mapping.  
  
 `newToken`  
 in Nuovo token di metadati a cui `oldToken` è stato nuovamente eseguito il mapping.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
