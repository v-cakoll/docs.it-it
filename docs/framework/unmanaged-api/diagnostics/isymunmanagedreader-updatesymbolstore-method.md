---
title: Metodo ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52a1f30612899fddc29af1a437fb9437e9a2b93c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490697"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>Metodo ISymUnmanagedReader::UpdateSymbolStore
Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta. Questo metodo viene utilizzato in scenari di modifica e continuazione per aggiornare l'archivio dei simboli in modo da corrispondere i delta per l'originale file eseguibile portabile (PE).  
  
> [!NOTE]
>  È necessario specificare solo una delle `filename` o `pIStream` parametri, non entrambi. Se `filename` viene specificato, l'archivio dei simboli verrà aggiornato con i simboli in tale file. Se `pIStream` viene specificato, l'archivio verrà aggiornato con i dati di <xref:System.Runtime.InteropServices.ComTypes.IStream>.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parametri  
 `filename`  
 [in] Il nome del file che contiene l'archivio dei simboli.  
  
 `pIStream`  
 [in] Il flusso di file, usato come alternativa per il `filename` parametro.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
