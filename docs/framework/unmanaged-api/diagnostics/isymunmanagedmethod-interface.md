---
title: Interfaccia ISymUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b19e5ce88ea34188b2757d2a0c313341fbf1e7e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604258"
---
# <a name="isymunmanagedmethod-interface"></a>Interfaccia ISymUnmanagedMethod
Rappresenta un metodo all'interno dell'archivio simboli. Questa interfaccia fornisce l'accesso al solo gli attributi di un metodo, anziché gli attributi relativi ai tipi correlate ai simboli.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|Ottiene lo spazio dei nomi all'interno del quale questo metodo è definito.|  
|[Metodo GetOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|Restituisce l'offset all'interno di questo metodo che corrisponde a una determinata posizione all'interno di un documento.|  
|[Metodo GetParameters](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|Ottiene i parametri per questo metodo.|  
|[Metodo GetRanges](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|Data una posizione in un documento, restituisce una matrice di coppie di offset iniziale e finale che corrispondono agli intervalli di Microsoft intermediate language (MSIL) che la posizione all'interno del metodo.|  
|[Metodo GetRootScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|Ottiene l'ambito lessicale di primo livello all'interno di questo metodo. Questo ambito racchiude l'intero metodo.|  
|[Metodo GetScopeFromOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|Ottiene l'ambito lessicale di maggiore inclusione all'interno di questo metodo che racchiude l'offset specificato.|  
|[Metodo GetSequencePointCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|Ottiene il conteggio dei punti di sequenza all'interno di questo metodo.|  
|[Metodo GetSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|Ottiene tutti i punti di sequenza all'interno di questo metodo.|  
|[Metodo GetSourceStartEnd](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|Ottiene le posizioni del documento iniziale e finale per l'origine di questo metodo.|  
|[Metodo GetToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|Restituisce il token di metadati per questo metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
