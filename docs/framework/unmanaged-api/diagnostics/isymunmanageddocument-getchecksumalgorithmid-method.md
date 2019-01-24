---
title: Metodo ISymUnmanagedDocument::GetCheckSumAlgorithmId
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c5861f598a653f433ffaa611d6f1be3ba6f69a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585604"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a>Metodo ISymUnmanagedDocument::GetCheckSumAlgorithmId
Ottiene l'identificatore dell'algoritmo di checksum, o restituisce un GUID di tutti gli zeri se non sono presenti checksum.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pRetVal`  
 [out] Puntatore a una variabile che riceve l'identificatore dell'algoritmo di checksum.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
