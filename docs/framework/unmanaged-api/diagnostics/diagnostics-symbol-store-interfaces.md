---
title: Interfacce dell'archivio dei simboli di diagnostica
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448532"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Interfacce dell'archivio dei simboli di diagnostica
Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da parte di un debugger.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Interfaccia IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 Fornisce metodi che visualizzano le informazioni di binding correnti sull'applicazione in esecuzione.  
  
 [Interfaccia IDebugAutoAttach](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 Definisce l'interfaccia per una connessione automatica al debugger richiamata dal server.  
  
 [Interfaccia INotifyConnection2](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 Dichiara i metodi per la registrazione e l'annullamento della registrazione di un'origine di notifica della connessione.  
  
 [Interfaccia INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 Dichiara i metodi per la notifica del sink.  
  
 [Interfaccia INotifySource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 Dichiara un metodo per l'impostazione dei filtri di notifica.  
  
 [Interfaccia ISymENCUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 Fornisce informazioni per la funzionalità di modifica e continuazione.  
  
 [Interfaccia ISymUnmanagedAsyncMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 Questa interfaccia è il complemento di lettura per l' [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Consente la definizione di informazioni facoltative sul metodo asincrono per ogni simbolo di metodo. Deve usare con un metodo aperto, ovvero tra le chiamate al [Metodo OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)e il [Metodo CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
 [Interfaccia ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 Rappresenta uno strumento di associazione di simboli per il codice non gestito.  
  
 [Interfaccia ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l'interfaccia `ISymUnmanagedBinder`.  
  
 [Interfaccia ISymUnmanagedBinder3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l'interfaccia `ISymUnmanagedBinder`.  
  
 [Interfaccia ISymUnmanagedConstant](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 Fornisce l'accesso alle costanti non gestite.  
  
 [Interfaccia ISymUnmanagedDispose](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 Elimina le risorse non gestite.  
  
 [Interfaccia ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 Rappresenta un documento al quale fa riferimento un archivio di simboli.  
  
 [Interfaccia ISymUnmanagedDocumentWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.  
  
 [Interfaccia ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 Fornisce metodi per la funzionalità di modifica e continuazione.  
  
 [Interfaccia ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 Rappresenta un metodo all'interno dell'archivio dei simboli.  
  
 [Interfaccia ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 Rappresenta uno spazio dei nomi.  
  
 [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.  
  
 [Interfaccia ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 Ottiene un metodo del lettore di simboli in base a un token di metodo e a un numero di versione di modifica e copia.  
  
 [Interfaccia ISymUnmanagedReaderSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 Fornisce metodi per ottenere informazioni sulla ricerca di simboli.  
  
 [Interfaccia ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 Rappresenta un ambito lessicale all'interno di un metodo.  
  
 [Interfaccia ISymUnmanagedScope2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 Rappresenta un ambito lessicale in un metodo ed estende l'interfaccia `ISymUnmanagedScope` con metodi che ottengono informazioni sulle costanti definite nell'ambito.  
  
 [Interfaccia ISymUnmanagedSourceServerModule](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 Fornisce i dati del server di origine per un modulo.  
  
 [Interfaccia ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 Fornisce metodi che consentono di ottenere informazioni sul percorso di ricerca.  
  
 [Interfaccia ISymUnmanagedVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.  
  
 [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.  
  
 [Interfaccia ISymUnmanagedWriter2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili. Estende l'interfaccia `ISymUnmanagedWriter`.  
  
 [Interfaccia ISymUnmanagedWriter3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili. Estende l'interfaccia `ISymUnmanagedWriter`.  
  
 [Interfaccia ISymUnmanagedWriter4](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 Interfaccia ISymUnmanagedWriter4.  
  
 [Interfaccia ISymUnmanagedWriter5](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 Interfaccia Metodo ISymUnmanagedWriter5.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Enumerazioni dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [Strutture dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
