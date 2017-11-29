---
title: Interfacce dell'archivio dei simboli di diagnostica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 50ef54c90609bf8ef1e3a943664daef95f50d926
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="diagnostics-symbol-store-interfaces"></a>Interfacce dell'archivio dei simboli di diagnostica
Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da un debugger.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [IBindingDisplay (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 Fornisce metodi che consentono di visualizzare informazioni correnti di associazione dell'applicazione in esecuzione.  
  
 [IDebugAutoAttach (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 Definisce l'interfaccia per la connessione automatico di un debugger richiamato al server.  
  
 [INotifyConnection2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 Dichiara i metodi per la registrazione e annullamento della registrazione di un'origine di notifica di connessione.  
  
 [INotifySink2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 Dichiara i metodi per la notifica di sink.  
  
 [INotifySource2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 Dichiara un metodo per impostare i filtri di notifica.  
  
 [ISymENCUnmanagedMethod (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 Vengono fornite informazioni per la funzionalità Modifica e continuazione.  
  
 [Interfaccia ISymUnmanagedAsyncMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 Questa interfaccia rappresenta il complemento di lettura per [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Consente la definizione delle informazioni sul metodo async facoltativo per ogni simbolo del metodo. Deve utilizzare con un metodo di aperto (vale a dire, tra le chiamate al [OpenMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)e [CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).  
  
 [Interfaccia ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 Rappresenta un raccoglitore di simboli per codice non gestito.  
  
 [ISymUnmanagedBinder2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.  
  
 [ISymUnmanagedBinder3 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.  
  
 [ISymUnmanagedConstant (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 Fornisce l'accesso alle costanti non gestite.  
  
 [ISymUnmanagedDispose (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 Elimina le risorse non gestite.  
  
 [Interfaccia ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 Rappresenta un documento al quale fa riferimento un archivio di simboli.  
  
 [ISymUnmanagedDocumentWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.  
  
 [ISymUnmanagedENCUpdate (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 Fornisce metodi per la funzionalità Modifica e continuazione.  
  
 [ISymUnmanagedMethod (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 Rappresenta un metodo all'interno dell'archivio simboli.  
  
 [ISymUnmanagedNamespace (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 Rappresenta uno spazio dei nomi.  
  
 [ISymUnmanagedReader (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio dei simboli.  
  
 [ISymUnmanagedReader2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 Ottiene un metodo del lettore di simboli specificato un token di metodo e un numero di versione di modifica e copia.  
  
 [ISymUnmanagedReaderSymbolSearchInfo (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 Fornisce metodi per ottenere informazioni sui simboli di ricerca.  
  
 [ISymUnmanagedScope (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 Rappresenta un ambito lessicale in un metodo.  
  
 [ISymUnmanagedScope2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 Rappresenta un ambito lessicale in un metodo ed estende il `ISymUnmanagedScope` interfaccia con metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito...  
  
 [ISymUnmanagedSourceServerModule (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 Fornisce i dati di server di origine per un modulo.  
  
 [ISymUnmanagedSymbolSearchInfo (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 Fornisce metodi per ottenere informazioni sul percorso di ricerca.  
  
 [ISymUnmanagedVariable (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.  
  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.  
  
 [ISymUnmanagedWriter2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti. Estende il `ISymUnmanagedWriter` interfaccia.  
  
 [ISymUnmanagedWriter3 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti. Estende il `ISymUnmanagedWriter` interfaccia.  
  
 [Interfaccia ISymUnmanagedWriter4](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 Interfaccia ISymUnmanagedWriter4.  
  
 [Interfaccia ISymUnmanagedWriter5](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 Interfaccia ISymUnmanagedWriter5.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Enumerazioni dell'archivio di simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [Strutture di archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
