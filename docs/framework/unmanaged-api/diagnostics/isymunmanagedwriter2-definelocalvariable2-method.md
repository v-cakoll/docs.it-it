---
title: Metodo ISymUnmanagedWriter2::DefineLocalVariable2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1124b57bed16e349c753be872c1b709a287e6237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>Metodo ISymUnmanagedWriter2::DefineLocalVariable2
Definisce una singola variabile nell'ambito lessicale corrente. Questo metodo può essere chiamato più volte per una variabile con lo stesso nome presente in più posizioni in un ambito. In questo caso, tuttavia, i valori del `startOffset` e `endOffset` parametri non devono sovrapporsi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 [in] Il nome della variabile locale.  
  
 `attributes`  
 [in] Attributi della variabile locale.  
  
 `sigToken`  
 [in] Il token di metadati della firma.  
  
 `addrKind`  
 [in] Il tipo di indirizzo.  
  
 `addr1`  
 [in] Il primo indirizzo per la specifica del parametro.  
  
 `addr2`  
 [in] Il secondo indirizzo per la specifica del parametro.  
  
 `addr3`  
 [in] Terzo indirizzo per la specifica del parametro.  
  
 `startOffset`  
 [in] Offset iniziale della variabile. Questo parametro è facoltativo. Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito. Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.  
  
 `endOffset`  
 [in] Offset finale della variabile. Questo parametro è facoltativo. Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito. Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [Metodo DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
