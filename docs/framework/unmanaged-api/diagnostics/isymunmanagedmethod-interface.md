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
ms.openlocfilehash: 728acc09f739fe567fca4a2571cbabf1ba8838a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedmethod-interface"></a>Interfaccia ISymUnmanagedMethod
Rappresenta un metodo all'interno dell'archivio simboli. Questa interfaccia fornisce l'accesso solo gli attributi relativi ai simboli di un metodo, anziché gli attributi relativi al tipo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|Ottiene lo spazio dei nomi all'interno del quale è definito questo metodo.|  
|[Metodo GetOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|Restituisce l'offset all'interno del metodo che corrisponde a una posizione specifica all'interno di un documento.|  
|[Metodo GetParameters](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|Ottiene i parametri per questo metodo.|  
|[Metodo GetRanges](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|Data una posizione in un documento, restituisce una matrice di coppie di offset iniziali e finali che corrispondono agli intervalli di Microsoft intermediate language (MSIL) che la posizione all'interno del metodo.|  
|[Metodo GetRootScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|Ottiene l'ambito lessicale di primo livello all'interno del metodo. Questo ambito racchiude l'intero metodo.|  
|[Metodo GetScopeFromOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|Ottiene l'ambito lessicale di maggiore inclusione all'interno del metodo che racchiude un offset specificato.|  
|[Metodo GetSequencePointCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|Ottiene il numero di punti di sequenza all'interno del metodo.|  
|[Metodo GetSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|Ottiene tutti i punti di sequenza all'interno del metodo.|  
|[Metodo GetSourceStartEnd](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|Ottiene le posizioni di documento di inizio e di fine per l'origine di questo metodo.|  
|[Metodo GetToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|Restituisce il token di metadati per questo metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
