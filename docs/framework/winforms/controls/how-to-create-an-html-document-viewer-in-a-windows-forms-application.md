---
title: 'Procedura: Creare un visualizzatore di documenti HTML in una Windows Forms Application'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 99609e4bf5a352c436986e0773375d1c8e15e790
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340750"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Procedura: Creare un visualizzatore di documenti HTML in una Windows Forms Application
È possibile usare il <xref:System.Windows.Forms.WebBrowser> controllo per visualizzare e stampare documenti HTML senza fornire la funzionalità completa di un browser Internet. Ciò è utile quando si desidera sfruttare le funzionalità di formattazione del codice HTML, ma non si desidera che gli utenti per caricare le pagine Web arbitrari che possono contenere i controlli Web non attendibili o codice di script potenzialmente dannosi. Si potrebbe voler limitare la capacità del <xref:System.Windows.Forms.WebBrowser> controllare in questo modo, ad esempio, per usarlo come un visualizzatore di posta elettronica HTML o per fornire la Guida in formato HTML nell'applicazione.  
  
### <a name="to-create-an-html-document-viewer"></a>Per creare un visualizzatore di documenti HTML  
  
1. Impostare il <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> proprietà `false` per impedire il <xref:System.Windows.Forms.WebBrowser> controllo da aprire i file trascinati su di esso.  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. Impostare il <xref:System.Windows.Forms.WebBrowser.Url%2A> proprietà al percorso del file iniziale da visualizzare.  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.  
  
-   Riferimenti agli assembly `System` e `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [Cenni preliminari sul controllo WebBrowser](webbrowser-control-overview.md)
- [Sicurezza dei controlli WebBrowser](webbrowser-security.md)
- [Procedura: Passare a un URL con il controllo WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Procedura: Stampare con un controllo WebBrowser](how-to-print-with-a-webbrowser-control.md)
