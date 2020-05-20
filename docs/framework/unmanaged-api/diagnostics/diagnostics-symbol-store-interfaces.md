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
ms.openlocfilehash: 044ed5e08a85442c5a73c123cf51529d2fd3f1fc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442176"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Interfacce dell'archivio dei simboli di diagnostica
Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da parte di un debugger.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Interfaccia IBindingDisplay](ibindingdisplay-interface.md)  
 Fornisce metodi che visualizzano le informazioni di binding correnti sull'applicazione in esecuzione.  
  
 [Interfaccia IDebugAutoAttach](idebugautoattach-interface.md)  
 Definisce l'interfaccia per una connessione automatica al debugger richiamata dal server.  
  
 [Interfaccia INotifyConnection2](inotifyconnection2-interface.md)  
 Dichiara i metodi per la registrazione e l'annullamento della registrazione di un'origine di notifica della connessione.  
  
 [Interfaccia INotifySink2](inotifysink2-interface.md)  
 Dichiara i metodi per la notifica del sink.  
  
 [Interfaccia INotifySource2](inotifysource2-interface.md)  
 Dichiara un metodo per l'impostazione dei filtri di notifica.  
  
 [Interfaccia ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)  
 Fornisce informazioni per la funzionalità di modifica e continuazione.  
  
 [Interfaccia ISymUnmanagedAsyncMethod](isymunmanagedasyncmethod-interface.md)  
 Questa interfaccia è il complemento di lettura per l' [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Consente la definizione di informazioni facoltative sul metodo asincrono per ogni simbolo di metodo. Deve usare con un metodo aperto, ovvero tra le chiamate al [Metodo OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)e il [Metodo CloseMethod](isymunmanagedwriter-closemethod-method.md).  
  
 [Interfaccia ISymUnmanagedBinder](isymunmanagedbinder-interface.md)  
 Rappresenta uno strumento di associazione di simboli per il codice non gestito.  
  
 [Interfaccia ISymUnmanagedBinder2](isymunmanagedbinder2-interface.md)  
 Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l' `ISymUnmanagedBinder` interfaccia.  
  
 [Interfaccia ISymUnmanagedBinder3](isymunmanagedbinder3-interface.md)  
 Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l' `ISymUnmanagedBinder` interfaccia.  
  
 [Interfaccia ISymUnmanagedConstant](isymunmanagedconstant-interface.md)  
 Fornisce l'accesso alle costanti non gestite.  
  
 [Interfaccia ISymUnmanagedDispose](isymunmanageddispose-interface.md)  
 Elimina le risorse non gestite.  
  
 [Interfaccia ISymUnmanagedDocument](isymunmanageddocument-interface.md)  
 Rappresenta un documento al quale fa riferimento un archivio di simboli.  
  
 [Interfaccia ISymUnmanagedDocumentWriter](isymunmanageddocumentwriter-interface.md)  
 Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.  
  
 [Interfaccia ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)  
 Fornisce metodi per la funzionalità di modifica e continuazione.  
  
 [Interfaccia ISymUnmanagedMethod](isymunmanagedmethod-interface.md)  
 Rappresenta un metodo all'interno dell'archivio dei simboli.  
  
 [Interfaccia ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)  
 Rappresenta uno spazio dei nomi.  
  
 [Interfaccia ISymUnmanagedReader](isymunmanagedreader-interface.md)  
 Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.  
  
 [Interfaccia ISymUnmanagedReader2](isymunmanagedreader2-interface.md)  
 Ottiene un metodo del lettore di simboli in base a un token di metodo e a un numero di versione di modifica e copia.  
  
 [Interfaccia ISymUnmanagedReaderSymbolSearchInfo](isymunmanagedreadersymbolsearchinfo-interface.md)  
 Fornisce metodi per ottenere informazioni sulla ricerca di simboli.  
  
 [Interfaccia ISymUnmanagedScope](isymunmanagedscope-interface.md)  
 Rappresenta un ambito lessicale all'interno di un metodo.  
  
 [Interfaccia ISymUnmanagedScope2](isymunmanagedscope2-interface.md)  
 Rappresenta un ambito lessicale in un metodo ed estende l' `ISymUnmanagedScope` interfaccia con metodi che ottengono informazioni sulle costanti definite nell'ambito.  
  
 [Interfaccia ISymUnmanagedSourceServerModule](isymunmanagedsourceservermodule-interface.md)  
 Fornisce i dati del server di origine per un modulo.  
  
 [Interfaccia ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md)  
 Fornisce metodi che consentono di ottenere informazioni sul percorso di ricerca.  
  
 [Interfaccia ISymUnmanagedVariable](isymunmanagedvariable-interface.md)  
 Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.  
  
 [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.  
  
 [Interfaccia ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili. Estende l' `ISymUnmanagedWriter` interfaccia.  
  
 [Interfaccia ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)  
 Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili. Estende l' `ISymUnmanagedWriter` interfaccia.  
  
 [Interfaccia ISymUnmanagedWriter4](isymunmanagedwriter4-interface.md)  
 Interfaccia ISymUnmanagedWriter4.  
  
 [Interfaccia ISymUnmanagedWriter5](isymunmanagedwriter5-interface.md)  
 Interfaccia Metodo ISymUnmanagedWriter5.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Enumerazioni dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-enumerations.md)  
  
 [Strutture dell'archivio simboli di diagnostica](diagnostics-symbol-store-structures.md)  
  
 [Debug](../debugging/index.md)
