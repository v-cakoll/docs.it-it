---
title: Metodo ISymUnmanagedWriter::OpenMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d63fb96635e34e07c3997c1aad838e67c70742
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropenmethod-method"></a>Metodo ISymUnmanagedWriter::OpenMethod
Apre un metodo nel quale simbolo vengono create le informazioni. Il metodo specificato diventa il metodo corrente per le chiamate definire punti di sequenza, parametri e gli ambiti lessicali. È un ambito lessicale implicito l'intero metodo. Riaprire un metodo che è stata chiusa in precedenza verranno cancellati i simboli definiti in precedenza per tale metodo. Può esistere un solo metodo aperto alla volta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a>Parametri  
 `method`  
 [in] Il token di metadati per il metodo da aprire.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [OpenMethod2 (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
