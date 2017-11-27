---
title: Metodo ISymUnmanagedWriter::OpenScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f56bc14b096b5086db1fc8d046ed699559381fb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriteropenscope-method"></a>Metodo ISymUnmanagedWriter::OpenScope
Apre un nuovo ambito lessicale nel metodo corrente. L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti. Gli ambiti devono formare una gerarchia. Elementi di pari livello non è consentiti si sovrappongono.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametri  
 `startOffset`  
 [in] L'offset della prima istruzione nell'ambito lessicale, in byte, dall'inizio del metodo.  
  
 `pRetVal`  
 [out] Un puntatore a un `ULONG32` che riceve l'identificatore di ambito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Note  
 `ISymUnmanagedWriter::OpenScope`Restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) per definire un ambito dell'offset iniziale e finale in un secondo momento. In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati. Gli identificatori di ambito sono validi solo nel metodo corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
