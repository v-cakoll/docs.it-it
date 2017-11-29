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
ms.openlocfilehash: 1e74e625c911f35bdb7c20451b1babd02cdb7658
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter-interface"></a>Interfaccia ISymUnmanagedWriter
Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Abort (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Chiude il writer di simboli senza eseguire il commit i simboli per l'archivio dei simboli.|  
|[Close (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Chiude il writer di simboli dopo il commit i simboli per l'archivio dei simboli.|  
|[CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Chiude il metodo corrente. Dopo un metodo è stato chiuso, non vi sono ulteriori simboli possono essere definiti all'interno di esso.|  
|[CloseNamespace (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Chiude l'ultimo aperto dello spazio dei nomi.|  
|[CloseScope (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Chiude l'ambito lessicale corrente.|  
|[DefineConstant (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Definisce un nome per un valore costante.|  
|[DefineDocument (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Definisce un documento di origine.|  
|[DefineField (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Definisce una singola variabile che non è presente all'interno di un metodo.|  
|[DefineGlobalVariable (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Definisce una singola variabile globale.|  
|[DefineLocalVariable (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Definisce una singola variabile nell'ambito lessicale corrente.|  
|[DefineParameter (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Definisce un singolo parametro nel metodo corrente.|  
|[DefineSequencePoints (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Definisce un gruppo di punti di sequenza nel metodo corrente.|  
|[GetDebugInfo (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Restituisce le informazioni necessarie per un compilatore per scrivere la voce di directory di debug nell'intestazione del file (PE) eseguibile portabile.|  
|[Initialize (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer e il nome del file di output in cui verranno scritti i simboli di debug.|  
|[Initialize2 (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer, imposta il nome del file di output a cui verranno scritti i simboli di debug e la posizione finale del file di database (PDB) del programma.|  
|[OpenMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Apre un metodo nel quale simbolo vengono create le informazioni.|  
|[OpenNamespace (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Apre un nuovo spazio dei nomi.|  
|[OpenScope (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Apre un nuovo ambito lessicale nel metodo corrente.|  
|[RemapToken (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Notifica il writer di simboli che è stato rimappato un token di metadati come i metadati è stato creato.|  
|[SetMethodSourceRange (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Specifica l'inizio e fine di un metodo all'interno di un file di origine.|  
|[SetScopeRange (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Definisce l'intervallo di offset per l'ambito lessicale specificato.|  
|[SetSymAttribute (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Definisce un attributo personalizzato in base al relativo nome.|  
|[SetUserEntryPoint (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Specifica il metodo definito dall'utente che è il punto di ingresso per questo modulo.|  
|[UsingNamespace (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Specifica il nome completo dello spazio dei nomi specificato viene utilizzato all'interno dell'ambito lessicale aperto.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedWriter2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [ISymUnmanagedWriter3 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
