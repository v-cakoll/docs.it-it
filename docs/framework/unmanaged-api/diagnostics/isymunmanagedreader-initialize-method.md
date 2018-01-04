---
title: Metodo ISymUnmanagedReader::Initialize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 433cd62f7801d386f3b34b7fc8e95bd1d0c5f765
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a>Metodo ISymUnmanagedReader::Initialize
Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che il lettore verrà associato, insieme al nome file del modulo.  
  
> [!NOTE]
>  Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di altri metodi di lettura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a>Parametri  
 `importer`  
 [in] L'interfaccia dell'utilità di importazione dei metadati al quale verrà associato questo reader.  
  
 `filename`  
 [in] Il nome file del modulo. È possibile utilizzare il `pIStream` parametro invece.  
  
 `searchPath`  
 [in] Il percorso di ricerca. Questo parametro è facoltativo.  
  
 `pIStream`  
 [in] Flusso di file, utilizzato come alternativa al parametro filename.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Note  
 È necessario specificare uno solo del `filename` o `pIStream` parametri, non entrambi. Il parametro `searchPath` è facoltativo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
