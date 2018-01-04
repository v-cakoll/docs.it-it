---
title: Interfaccia ISymUnmanagedWriter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter
helpviewer_keywords: ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4996f0196df4c2bcf890df6ad972f313403e435
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter-interface"></a>Interfaccia ISymUnmanagedWriter
Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Chiude il writer di simboli senza eseguire il commit i simboli per l'archivio dei simboli.|  
|[Metodo Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Chiude il writer di simboli dopo il commit i simboli per l'archivio dei simboli.|  
|[Metodo CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Chiude il metodo corrente. Dopo un metodo è stato chiuso, non vi sono ulteriori simboli possono essere definiti all'interno di esso.|  
|[Metodo CloseNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Chiude l'ultimo aperto dello spazio dei nomi.|  
|[Metodo CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Chiude l'ambito lessicale corrente.|  
|[Metodo DefineConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Definisce un nome per un valore costante.|  
|[Metodo DefineDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Definisce un documento di origine.|  
|[Metodo DefineField](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Definisce una singola variabile che non è presente all'interno di un metodo.|  
|[Metodo DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Definisce una singola variabile globale.|  
|[Metodo DefineLocalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Definisce una singola variabile nell'ambito lessicale corrente.|  
|[Metodo DefineParameter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Definisce un singolo parametro nel metodo corrente.|  
|[Metodo DefineSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Definisce un gruppo di punti di sequenza nel metodo corrente.|  
|[Metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Restituisce le informazioni necessarie per un compilatore per scrivere la voce di directory di debug nell'intestazione del file (PE) eseguibile portabile.|  
|[Metodo Initialize](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer e il nome del file di output in cui verranno scritti i simboli di debug.|  
|[Metodo Initialize2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer, imposta il nome del file di output a cui verranno scritti i simboli di debug e la posizione finale del file di database (PDB) del programma.|  
|[Metodo OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Apre un metodo nel quale simbolo vengono create le informazioni.|  
|[Metodo OpenNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Apre un nuovo spazio dei nomi.|  
|[Metodo OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Apre un nuovo ambito lessicale nel metodo corrente.|  
|[Metodo RemapToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Notifica il writer di simboli che è stato rimappato un token di metadati come i metadati è stato creato.|  
|[Metodo SetMethodSourceRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Specifica l'inizio e fine di un metodo all'interno di un file di origine.|  
|[Metodo SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Definisce l'intervallo di offset per l'ambito lessicale specificato.|  
|[Metodo SetSymAttribute](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Definisce un attributo personalizzato in base al relativo nome.|  
|[Metodo SetUserEntryPoint](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Specifica il metodo definito dall'utente che è il punto di ingresso per questo modulo.|  
|[Metodo UsingNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Specifica il nome completo dello spazio dei nomi specificato viene utilizzato all'interno dell'ambito lessicale aperto.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [Interfaccia ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [Interfaccia ISymUnmanagedWriter3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
