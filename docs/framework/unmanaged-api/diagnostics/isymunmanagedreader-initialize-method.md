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
ms.openlocfilehash: f2dceeb2f0b3aa9f3147157e77087dffbf2d5f85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939017"
---
# <a name="isymunmanagedreaderinitialize-method"></a>Metodo ISymUnmanagedReader::Initialize
Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati a cui verrà associato questo Reader, insieme al nome file del modulo.  
  
> [!NOTE]
> Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di qualsiasi altro metodo Reader.  
  
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
 in Interfaccia dell'utilità di importazione dei metadati a cui verrà associato il lettore.  
  
 `filename`  
 in Nome file del modulo. In alternativa, è `pIStream` possibile usare il parametro.  
  
 `searchPath`  
 in Percorso in cui eseguire la ricerca. Questo parametro è facoltativo.  
  
 `pIStream`  
 in Il flusso di file, usato come alternativa al parametro filename.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Note  
 È necessario specificare solo uno dei `filename` `pIStream` parametri o, non entrambi. Il parametro `searchPath` è facoltativo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
