---
title: Cenni preliminari sul controllo WebBrowser
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 2e69b71b3e354101d950d6f7011b13fc7c0de030
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540992"
---
# <a name="webbrowser-control-overview"></a>Cenni preliminari sul controllo WebBrowser
Il <xref:System.Windows.Forms.WebBrowser> controllo fornisce un wrapper gestito per il controllo WebBrowser ActiveX. Il wrapper gestito consente di visualizzare le pagine Web in applicazioni client Windows Form. È possibile utilizzare il <xref:System.Windows.Forms.WebBrowser> controllo per duplicare la funzionalità di esplorazione Web di Internet Explorer nell'applicazione oppure è possibile disabilitare funzionalità predefinite di Internet Explorer e utilizzare il controllo come visualizzatore di documenti HTML semplice. È inoltre possibile utilizzare il controllo per aggiungere al form di elementi dell'interfaccia utente basati su DHTML e nascondere il fatto che sono ospitati nel <xref:System.Windows.Forms.WebBrowser> controllo. Questo approccio consente di combinare facilmente controlli Web e i controlli Windows Form in una singola applicazione.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Proprietà utilizzate di frequente, metodi ed eventi  
 Il <xref:System.Windows.Forms.WebBrowser> controllo ha diverse proprietà, metodi ed eventi che è possibile utilizzare per implementare i controlli disponibili in Internet Explorer. Ad esempio, è possibile utilizzare il `Navigate` metodo per implementare una barra degli indirizzi e `GoBack`, `GoForward`, `Stop`, e `Refresh` metodi per implementare i pulsanti di navigazione in una barra degli strumenti. È possibile gestire il `Navigated` evento per aggiornare la barra degli indirizzi con il valore della `Url` proprietà e la barra del titolo con il valore della `DocumentTitle` proprietà.  
  
 Se si desidera generare i propri dati di pagina all'interno dell'applicazione, è possibile impostare il `DocumentText` proprietà. Se si ha familiarità con il modello a oggetti documento (DOM) HTML, è inoltre possibile modificare il contenuto della pagina Web corrente tramite il `Document` proprietà. Questa proprietà, è possibile archiviare e modificare i documenti in memoria anziché spostarsi tra i file.  
  
 Il `Document` proprietà consente inoltre di chiamare i metodi implementati nella pagina Web dal codice dell'applicazione client il codice di script. Per accedere a codice dell'applicazione client dal codice di script, impostare il `ObjectForScripting` proprietà. L'oggetto specificato è possibile accedere al codice di script come il `window.external` oggetto.  
  
|nome|Descrizione|  
|----------|-----------------|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A>|Ottiene un oggetto che fornisce l'accesso gestito al modello di oggetto di documento (DOM) HTML della pagina Web corrente.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Evento|Si verifica quando una pagina Web al termine del caricamento.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Ottiene o imposta il codice HTML il contenuto della pagina Web corrente.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Ottiene il titolo della pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Consente di passare alla pagina precedente nella cronologia.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Consente di passare alla pagina successiva nella cronologia.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Consente di passare all'URL specificato.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating> Evento|Si verifica prima dello spostamento, consentendo l'annullamento dell'azione.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Ottiene o imposta un oggetto che è possibile utilizzare script di codice della pagina Web per comunicare con l'applicazione.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Print%2A>|Consente di stampare la pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Ricarica la pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Il processo si interromperà la navigazione corrente e si arresta elemento dinamico della pagina, ad esempio i suoni e animazioni.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.Url%2A>|Ottiene o imposta l'URL della pagina Web corrente. Impostazione di questa proprietà consente di passare il controllo al nuovo URL.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>  
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserReadyState>  
 <xref:System.Windows.Forms.WebBrowserRefreshOption>  
 [Procedura: Passare a un URL con il controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [Procedura: Stampare con un controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 [Procedura: Aggiungere funzionalità del browser Web a una Windows Forms Application](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 [Procedura: Creare un visualizzatore di documenti HTML in una Windows Forms Application](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 [Procedura: Implementare comunicazioni bidirezionali tra il codice DHTML e il codice dell'applicazione client](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 [Sicurezza dei controlli WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)
