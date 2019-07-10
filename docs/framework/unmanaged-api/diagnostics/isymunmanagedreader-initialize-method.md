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
ms.openlocfilehash: 1986ed730c6f0a1ba8a2d8e3c688e6872184da9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736761"
---
# <a name="isymunmanagedreaderinitialize-method"></a>Metodo ISymUnmanagedReader::Initialize
Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che verrà associato, insieme al nome file del modulo di questo lettore.  
  
> [!NOTE]
>  Questo metodo può essere chiamato una sola volta e deve essere chiamato prima degli altri metodi di lettura.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
