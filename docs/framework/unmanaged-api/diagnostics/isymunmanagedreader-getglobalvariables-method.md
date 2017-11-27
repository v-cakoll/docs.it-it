---
title: Metodo ISymUnmanagedReader::GetGlobalVariables
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetGlobalVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cad85da193220c766da393a753501400e698ee8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a>Metodo ISymUnmanagedReader::GetGlobalVariables
Restituisce tutte le variabili globali.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cVars`  
 [in] La lunghezza del buffer a cui puntava `pcVars`.  
  
 `pcVars`  
 [out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le variabili.  
  
 `pVars`  
 [out] Un buffer che contiene le variabili.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [ISymUnmanagedReader (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
