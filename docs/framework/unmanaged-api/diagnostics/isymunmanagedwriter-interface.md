---
title: Interfaccia ISymUnmanagedWriter
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter
helpviewer_keywords:
- ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type:
- apiref
ms.openlocfilehash: 8f0bbd26bde562df5482d167c9d2775e01426f55
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610054"
---
# <a name="isymunmanagedwriter-interface"></a>Interfaccia ISymUnmanagedWriter
Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](isymunmanagedwriter-abort-method.md)|Chiude il writer di simboli senza eseguire il commit dei simboli nell'archivio dei simboli.|  
|[Close (metodo)](isymunmanagedwriter-close-method.md)|Chiude il writer di simboli dopo aver eseguito il commit dei simboli nell'archivio dei simboli.|  
|[Metodo CloseMethod](isymunmanagedwriter-closemethod-method.md)|Chiude il metodo corrente. Una volta chiuso un metodo, non è possibile definire altri simboli al suo interno.|  
|[Metodo CloseNamespace](isymunmanagedwriter-closenamespace-method.md)|Chiude lo spazio dei nomi aperto più di recente.|  
|[Metodo CloseScope](isymunmanagedwriter-closescope-method.md)|Chiude l'ambito lessicale corrente.|  
|[Metodo DefineConstant](isymunmanagedwriter-defineconstant-method.md)|Definisce un nome per un valore costante.|  
|[Metodo DefineDocument](isymunmanagedwriter-definedocument-method.md)|Definisce un documento di origine.|  
|[Metodo DefineField](isymunmanagedwriter-definefield-method.md)|Definisce una singola variabile che non si trova all'interno di un metodo.|  
|[Metodo DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)|Definisce una variabile globale singola.|  
|[Metodo DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)|Definisce una singola variabile nell'ambito lessicale corrente.|  
|[Metodo DefineParameter](isymunmanagedwriter-defineparameter-method.md)|Definisce un singolo parametro nel metodo corrente.|  
|[Metodo DefineSequencePoints](isymunmanagedwriter-definesequencepoints-method.md)|Definisce un gruppo di punti di sequenza nel metodo corrente.|  
|[Metodo GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md)|Restituisce le informazioni necessarie affinché un compilatore scriva la voce della directory di debug nell'intestazione del file eseguibile Portable (PE).|  
|[Metodo Initialize](isymunmanagedwriter-initialize-method.md)|Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato e imposta il nome del file di output in cui verranno scritti i simboli di debug.|  
|[Metodo Initialize2](isymunmanagedwriter-initialize2-method.md)|Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato, imposta il nome del file di output in cui verranno scritti i simboli di debug e imposta la posizione finale del file del database di programma (PDB).|  
|[Metodo OpenMethod](isymunmanagedwriter-openmethod-method.md)|Apre un metodo in cui vengono emesse le informazioni sui simboli.|  
|[Metodo OpenNamespace](isymunmanagedwriter-opennamespace-method.md)|Apre un nuovo spazio dei nomi.|  
|[Metodo OpenScope](isymunmanagedwriter-openscope-method.md)|Apre un nuovo ambito lessicale nel metodo corrente.|  
|[Metodo RemapToken](isymunmanagedwriter-remaptoken-method.md)|Notifica al writer di simboli che è stato eseguito il mapping di un token di metadati durante la creazione dei metadati.|  
|[Metodo SetMethodSourceRange](isymunmanagedwriter-setmethodsourcerange-method.md)|Specifica l'inizio e la fine effettivi di un metodo in un file di origine.|  
|[Metodo SetScopeRange](isymunmanagedwriter-setscoperange-method.md)|Definisce l'intervallo di offset per l'ambito lessicale specificato.|  
|[Metodo SetSymAttribute](isymunmanagedwriter-setsymattribute-method.md)|Definisce un attributo personalizzato in base al nome.|  
|[Metodo SetUserEntryPoint](isymunmanagedwriter-setuserentrypoint-method.md)|Specifica il metodo definito dall'utente che rappresenta il punto di ingresso per questo modulo.|  
|[Metodo UsingNamespace](isymunmanagedwriter-usingnamespace-method.md)|Specifica che il nome dello spazio dei nomi completo specificato viene utilizzato all'interno dell'ambito lessicale attualmente aperto.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
- [Interfaccia ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
