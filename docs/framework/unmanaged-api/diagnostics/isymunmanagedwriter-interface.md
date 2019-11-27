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
ms.openlocfilehash: fc19ee25e903046daef376e4297c8feb3d01ad47
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427929"
---
# <a name="isymunmanagedwriter-interface"></a>Interfaccia ISymUnmanagedWriter
Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Chiude il writer di simboli senza eseguire il commit dei simboli nell'archivio dei simboli.|  
|[Metodo Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Chiude il writer di simboli dopo aver eseguito il commit dei simboli nell'archivio dei simboli.|  
|[Metodo CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Chiude il metodo corrente. Una volta chiuso un metodo, non è possibile definire altri simboli al suo interno.|  
|[Metodo CloseNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Chiude lo spazio dei nomi aperto più di recente.|  
|[Metodo CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Chiude l'ambito lessicale corrente.|  
|[Metodo DefineConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Definisce un nome per un valore costante.|  
|[Metodo DefineDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Definisce un documento di origine.|  
|[Metodo DefineField](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Definisce una singola variabile che non si trova all'interno di un metodo.|  
|[Metodo DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Definisce una singola variabile globale.|  
|[Metodo DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Definisce una singola variabile nell'ambito lessicale corrente.|  
|[Metodo DefineParameter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Definisce un singolo parametro nel metodo corrente.|  
|[Metodo DefineSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Definisce un gruppo di punti di sequenza nel metodo corrente.|  
|[Metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Restituisce le informazioni necessarie affinché un compilatore scriva la voce della directory di debug nell'intestazione del file eseguibile Portable (PE).|  
|[Metodo Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato e imposta il nome del file di output in cui verranno scritti i simboli di debug.|  
|[Metodo Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato, imposta il nome del file di output in cui verranno scritti i simboli di debug e imposta la posizione finale del file del database di programma (PDB).|  
|[Metodo OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Apre un metodo in cui vengono emesse le informazioni sui simboli.|  
|[Metodo OpenNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Apre un nuovo spazio dei nomi.|  
|[Metodo OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Apre un nuovo ambito lessicale nel metodo corrente.|  
|[Metodo RemapToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Notifica al writer di simboli che è stato eseguito il mapping di un token di metadati durante la creazione dei metadati.|  
|[Metodo SetMethodSourceRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Specifica l'inizio e la fine reali di un metodo all'interno di un file di origine.|  
|[Metodo SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Definisce l'intervallo di offset per l'ambito lessicale specificato.|  
|[Metodo SetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Definisce un attributo personalizzato in base al nome.|  
|[Metodo SetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Specifica il metodo definito dall'utente che rappresenta il punto di ingresso per questo modulo.|  
|[Metodo UsingNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Specifica che il nome dello spazio dei nomi completo specificato viene utilizzato all'interno dell'ambito lessicale attualmente aperto.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [Interfaccia ISymUnmanagedWriter3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
