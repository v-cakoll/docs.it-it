---
title: Metodo ISymUnmanagedReader::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 661c27b9c21f77104b8a86163d3c92d44f8a85df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669975"
---
# <a name="isymunmanagedreaderinitialize-method"></a>Metodo ISymUnmanagedReader::Initialize
Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che verrà associato, insieme al nome file del modulo di questo lettore.  
  
> [!NOTE]
>  Questo metodo può essere chiamato una sola volta e deve essere chiamato prima degli altri metodi di lettura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>Parametri  
 `importer`  
 [in] L'interfaccia dell'utilità di importazione di metadati con cui verrà associato questo lettore.  
  
 `filename`  
 [in] Nome file del modulo. È possibile usare il `pIStream` parametro invece.  
  
 `searchPath`  
 [in] Il percorso di ricerca. Questo parametro è facoltativo.  
  
 `pIStream`  
 [in] Il flusso di file, usato come alternativa per il parametro filename.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="remarks"></a>Note  
 È necessario specificare solo uno dei `filename` o il `pIStream` parametri, non entrambi. Il parametro `searchPath` è facoltativo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
