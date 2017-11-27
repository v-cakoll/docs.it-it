---
title: Metodo ISymUnmanagedWriter2::DefineGlobalVariable2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineGlobalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d1214a7bc8cb2826e31c310c88bce8158aefd4f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a>Metodo ISymUnmanagedWriter2::DefineGlobalVariable2
Definisce una singola variabile globale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 [in] Il nome della variabile globale.  
  
 `attributes`  
 [in] Attributi della variabile globale.  
  
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
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedWriter2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [DefineGlobalVariable (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
