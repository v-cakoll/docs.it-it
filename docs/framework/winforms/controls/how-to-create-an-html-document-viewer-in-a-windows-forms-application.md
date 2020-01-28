---
title: Creare un visualizzatore di documenti HTML in un'app Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732840"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Procedura: creare un visualizzatore di documenti HTML in un'applicazione Windows Form
È possibile utilizzare il controllo <xref:System.Windows.Forms.WebBrowser> per visualizzare e stampare i documenti HTML senza fornire le funzionalità complete di un Web browser Internet. Questa opzione è utile quando si desidera sfruttare le funzionalità di formattazione di HTML, ma non si desidera che gli utenti carichino pagine Web arbitrarie che possono contenere controlli Web non attendibili o codice di script potenzialmente dannoso. È possibile limitare la funzionalità del controllo <xref:System.Windows.Forms.WebBrowser> in questo modo, ad esempio, per usarlo come visualizzatore di posta elettronica HTML o per fornire la Guida in formato HTML nell'applicazione.  
  
### <a name="to-create-an-html-document-viewer"></a>Per creare un visualizzatore di documenti HTML  
  
1. Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> su `false` per impedire che il controllo <xref:System.Windows.Forms.WebBrowser> apra i file eliminati.  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. Impostare la proprietà <xref:System.Windows.Forms.WebBrowser.Url%2A> sul percorso del file iniziale da visualizzare.  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.  
  
- Riferimenti agli assembly `System` e `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [Panoramica sul controllo WebBrowser](webbrowser-control-overview.md)
- [Sicurezza dei controlli WebBrowser](webbrowser-security.md)
- [Procedura: Passare a un URL con il controllo WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Procedura: Stampare con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md)
