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
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615124"
---
# <a name="isymunmanagedmethod-interface"></a>Interfaccia ISymUnmanagedMethod
Rappresenta un metodo all'interno dell'archivio dei simboli. Questa interfaccia consente di accedere solo agli attributi relativi ai simboli di un metodo, anziché agli attributi correlati al tipo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetNamespace](isymunmanagedmethod-getnamespace-method.md)|Ottiene lo spazio dei nomi in cui è definito il metodo.|  
|[Metodo GetOffset](isymunmanagedmethod-getoffset-method.md)|Restituisce l'offset all'interno di questo metodo che corrisponde a una posizione specificata all'interno di un documento.|  
|[Metodo GetParameters](isymunmanagedmethod-getparameters-method.md)|Ottiene i parametri per questo metodo.|  
|[Metodo GetRanges](isymunmanagedmethod-getranges-method.md)|Data una posizione in un documento, restituisce una matrice di coppie di offset di inizio e di fine che corrispondono agli intervalli di MSIL (Microsoft Intermediate Language) che la posizione copre all'interno di questo metodo.|  
|[Metodo GetRootScope](isymunmanagedmethod-getrootscope-method.md)|Ottiene l'ambito lessicale radice all'interno di questo metodo. Questo ambito racchiude l'intero metodo.|  
|[Metodo GetScopeFromOffset](isymunmanagedmethod-getscopefromoffset-method.md)|Ottiene l'ambito lessicale di maggiore inclusione all'interno di questo metodo che racchiude l'offset specificato.|  
|[Metodo GetSequencePointCount](isymunmanagedmethod-getsequencepointcount-method.md)|Ottiene il conteggio dei punti di sequenza all'interno di questo metodo.|  
|[Metodo GetSequencePoints](isymunmanagedmethod-getsequencepoints-method.md)|Ottiene tutti i punti di sequenza all'interno di questo metodo.|  
|[Metodo GetSourceStartEnd](isymunmanagedmethod-getsourcestartend-method.md)|Ottiene le posizioni del documento iniziale e finale per l'origine di questo metodo.|  
|[Metodo GetToken](isymunmanagedmethod-gettoken-method.md)|Restituisce il token di metadati per il metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
