---
title: Cenni preliminari sul controllo WebBrowser
description: Informazioni su come usare il controllo WebBrowser per combinare facilmente i controlli Web con Windows Forms controlli in una singola applicazione.
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 6a0548bb0f5905d8f848ab13fb82d32b50caa891
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325736"
---
# <a name="webbrowser-control-overview"></a>Cenni preliminari sul controllo WebBrowser
Il <xref:System.Windows.Forms.WebBrowser> controllo fornisce un wrapper gestito per il controllo ActiveX WebBrowser. Il wrapper gestito consente di visualizzare le pagine Web nelle applicazioni client Windows Forms. È possibile utilizzare il <xref:System.Windows.Forms.WebBrowser> controllo per duplicare la funzionalità di esplorazione Web di Internet Explorer nell'applicazione oppure è possibile disabilitare la funzionalità predefinita di Internet Explorer e utilizzare il controllo come semplice visualizzatore di documenti HTML. È anche possibile usare il controllo per aggiungere elementi dell'interfaccia utente basati su DHTML al form e nascondere il fatto che sono ospitati nel <xref:System.Windows.Forms.WebBrowser> controllo. Questo approccio consente di combinare facilmente i controlli Web con Windows Forms controlli in un'unica applicazione.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Proprietà, metodi ed eventi usati di frequente  
 Il <xref:System.Windows.Forms.WebBrowser> controllo dispone di diverse proprietà, metodi ed eventi che è possibile utilizzare per implementare i controlli disponibili in Internet Explorer. Ad esempio, è possibile usare il `Navigate` metodo per implementare una barra degli indirizzi e i `GoBack` metodi,, `GoForward` `Stop` e `Refresh` per implementare i pulsanti di navigazione su una barra degli strumenti. È possibile gestire l' `Navigated` evento per aggiornare la barra degli indirizzi con il valore della `Url` proprietà e la barra del titolo con il valore della `DocumentTitle` Proprietà.  
  
 Se si vuole generare il proprio contenuto della pagina all'interno dell'applicazione, è possibile impostare la `DocumentText` Proprietà. Se si ha familiarità con il modello DOM (Document Object Model) HTML, è anche possibile modificare il contenuto della pagina Web corrente tramite la `Document` Proprietà. Con questa proprietà è possibile archiviare e modificare i documenti in memoria anziché spostarsi tra i file.  
  
 La `Document` proprietà consente anche di chiamare i metodi implementati nel codice di script della pagina Web dal codice dell'applicazione client. Per accedere al codice dell'applicazione client dal codice di scripting, impostare la `ObjectForScripting` Proprietà. È possibile accedere all'oggetto specificato dal codice di script come `window.external` oggetto.  
  
|Nome|Description|  
|----------|-----------------|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.Document%2A>|Ottiene un oggetto che fornisce l'accesso gestito al DOM (Document Object Model) HTML della pagina Web corrente.|  
|Evento<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>|Si verifica al termine del caricamento di una pagina Web.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Ottiene o imposta il contenuto HTML della pagina Web corrente.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Ottiene il titolo della pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Passa alla pagina precedente nella cronologia.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Passa alla pagina successiva della cronologia.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Consente di passare all'URL specificato.|  
|Evento<xref:System.Windows.Forms.WebBrowser.Navigating>|Si verifica prima dell'inizio della navigazione, consentendo l'annullamento dell'azione.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Ottiene o imposta un oggetto che può essere utilizzato dal codice di scripting di pagine Web per comunicare con l'applicazione.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Print%2A>|Stampa la pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Ricarica la pagina Web corrente.|  
|Metodo <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Arresta l'esplorazione corrente e arresta gli elementi dinamici della pagina, quali suoni e animazioni.|  
|Proprietà <xref:System.Windows.Forms.WebBrowser.Url%2A>|Ottiene o imposta l'URL della pagina Web corrente. Impostando questa proprietà, il controllo viene spostato sul nuovo URL.|  
  
## <a name="see-also"></a>Vedi anche

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
- [Procedura: passare a un URL con il controllo WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Procedura: stampare con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md)
- [Procedura: Aggiungere funzionalità del browser Web a un'applicazione Windows Forms](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [Procedura: creare un visualizzatore di documenti HTML in un'applicazione Windows Form](how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [Procedura: implementare comunicazioni bidirezionali tra il codice DHTML e il codice dell'applicazione client](implement-two-way-com-between-dhtml-and-client.md)
- [Sicurezza dei controlli WebBrowser](webbrowser-security.md)
