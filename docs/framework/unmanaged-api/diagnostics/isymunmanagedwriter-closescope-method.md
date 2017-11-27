---
title: Metodo ISymUnmanagedWriter::CloseScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8df22e5f9ea2ca294f502fcebf4b2ed5cd7900d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a>Metodo ISymUnmanagedWriter::CloseScope
Chiude l'ambito lessicale corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a>Parametri  
 `endOffset`  
 [in] L'offset dall'inizio del metodo del punto alla fine dell'ultima istruzione nell'ambito lessicale, in byte.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Note  
 Una volta chiuso un ambito, non più variabili possono essere definite all'interno di esso.  
  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) per definire successivamente un ambito dell'offset iniziale e finale. In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` saranno ignorati. Gli identificatori di ambito sono validi solo nel metodo corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
