---
title: Metodo ISymUnmanagedDocument::GetSourceRange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6c47f1f491b184e9abe9d56d0729100b0d9b36a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>Metodo ISymUnmanagedDocument::GetSourceRange
Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato. Il buffer deve essere sufficientemente grande da contenere l'origine.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `startLine`  
 [in] Riga iniziale nel documento corrente.  
  
 `startColumn`  
 [in] La colonna iniziale del documento corrente.  
  
 `endLine`  
 [in] La riga finale nel documento corrente.  
  
 `endColumn`  
 [in] La colonna finale nel documento corrente.  
  
 `cSourceBytes`  
 [in] Le dimensioni dell'origine, in byte.  
  
 `pcSourceBytes`  
 [out] Puntatore a una variabile che riceve le dimensioni di origine.  
  
 `source`  
 [out] Le dimensioni e la lunghezza dell'intervallo specificato del documento di origine, in byte.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
