---
title: Cenni preliminari sul controllo WebBrowser
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 919098fd5eb6578b91a7b44cf99ba3aef9076081
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610981"
---
# <a name="webbrowser-control-overview"></a>Cenni preliminari sul controllo WebBrowser
Il <xref:System.Windows.Forms.WebBrowser> controllo fornisce un wrapper gestito per il controllo WebBrowser ActiveX. Il wrapper gestito consente di visualizzare le pagine Web nelle applicazioni client Windows Form. È possibile usare il <xref:System.Windows.Forms.WebBrowser> controllo per duplicare funzionalità del browser Web Internet Explorer nell'applicazione oppure è possibile disabilitare la funzionalità predefinite di Internet Explorer e usare il controllo come visualizzatore di documenti HTML semplice. È anche possibile usare il controllo da aggiungere al form di elementi dell'interfaccia utente basati su DHTML e nascondere il fatto che sono ospitati nel <xref:System.Windows.Forms.WebBrowser> controllo. Questo approccio consente di combinare senza problemi i controlli con i controlli Windows Form in una singola applicazione Web.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Proprietà usate di frequente, metodi ed eventi  
 Il <xref:System.Windows.Forms.WebBrowser> controllo ha diverse proprietà, metodi ed eventi che è possibile usare per implementare i controlli disponibili in Internet Explorer. Ad esempio, è possibile usare la `Navigate` metodo per implementare una barra degli indirizzi e il `GoBack`, `GoForward`, `Stop`, e `Refresh` metodi da implementare pulsanti di navigazione in una barra degli strumenti. È possibile gestire il `Navigated` evento da aggiornare la barra degli indirizzi con il valore della `Url` proprietà e la barra del titolo con il valore della `DocumentTitle` proprietà.  
  
 Se si desidera generare il proprio contenuto della pagina all'interno dell'applicazione, è possibile impostare il `DocumentText` proprietà. Se si ha familiarità con il modello a oggetti documento (DOM) HTML, è inoltre possibile modificare il contenuto della pagina Web corrente tramite il `Document` proprietà. Questa proprietà, è possibile archiviare e modificare i documenti in memoria anziché navigare tra i vari file.  
  
 Il `Document` proprietà consente inoltre di chiamare i metodi implementati in codice dal codice dell'applicazione client di script delle pagine Web. Per accedere a codice dell'applicazione client dal codice di script, impostare il `ObjectForScripting` proprietà. L'oggetto specificato sono accessibili al codice di script come il `window.external` oggetto.  
  
|nome|Descrizione|  
|----------|-----------------|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A>|Ottiene un oggetto che fornisce l'accesso gestito per il modello di oggetto di documento (DOM) HTML della pagina Web corrente.|  
|Evento<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> |Si verifica quando una pagina Web al termine del caricamento.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Ottiene o imposta il codice HTML del contenuto della pagina Web corrente.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Ottiene il titolo della pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Consente di passare alla pagina precedente nella cronologia.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Consente di passare alla pagina successiva nella cronologia.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Consente di passare all'URL specificato.|  
|Evento<xref:System.Windows.Forms.WebBrowser.Navigating> |Si verifica prima dello spostamento, consentendo l'annullamento dell'azione.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Ottiene o imposta un oggetto che è possibile usare script di codice della pagina Web per comunicare con l'applicazione.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Print%2A>|Consente di stampare la pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Ricarica la pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Il processo si interromperà la navigazione corrente e si arresta elemento dinamico della pagina, ad esempio i suoni e animazioni.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.Url%2A>|Ottiene o imposta l'URL della pagina Web corrente. Impostazione di questa proprietà consente di passare il controllo al nuovo URL.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>
- <xref:System.Windows.Forms.WebBrowserEncryptionLevel>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>
- <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>
- <xref:System.Windows.Forms.WebBrowserReadyState>
- <xref:System.Windows.Forms.WebBrowserRefreshOption>
- [Procedura: Passare a un URL con il controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Procedura: Stampa con un controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
- [Procedura: Aggiungere funzionalità del Browser Web a un'applicazione di Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [Procedura: Creare un visualizzatore di documenti HTML in una Windows Forms Application](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [Procedura: Implementare comunicazioni bidirezionali tra codice DHTML e il codice dell'applicazione Client](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)
- [Sicurezza dei controlli WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)
