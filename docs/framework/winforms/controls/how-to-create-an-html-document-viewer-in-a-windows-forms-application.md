---
title: 'Procedura: Creare un visualizzatore di documenti HTML in un''applicazione Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e06fbfde68c0d02a94f8c7e4657e2907cd3fa7eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Procedura: Creare un visualizzatore di documenti HTML in un'applicazione Windows Forms
È possibile utilizzare il <xref:System.Windows.Forms.WebBrowser> controllo per visualizzare e stampare documenti HTML senza fornire la funzionalità completa di un browser Internet. Ciò è utile quando si desidera avvalersi delle funzionalità di formattazione HTML, ma non si desidera che gli utenti per caricare pagine Web arbitrarie che può contenere i controlli Web non attendibili o codice di script potenzialmente dannosi. È possibile limitare la capacità del <xref:System.Windows.Forms.WebBrowser> controllare in questo modo, ad esempio, per utilizzarlo come visualizzatore HTML tramite posta elettronica o per fornire la Guida in formato HTML nell'applicazione.  
  
### <a name="to-create-an-html-document-viewer"></a>Per creare un visualizzatore di documenti HTML  
  
1.  Impostare il <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> proprietà `false` per impedire il <xref:System.Windows.Forms.WebBrowser> aprire i file trascinati nel controllo.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  Impostare il <xref:System.Windows.Forms.WebBrowser.Url%2A> proprietà al percorso del file iniziale da visualizzare.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.WebBrowser> denominato `webBrowser1`.  
  
-   Riferimenti agli assembly `System` e `System.Windows.Forms`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [Panoramica sul controllo WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [Sicurezza dei controlli WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [Procedura: Passare a un URL con il controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [Procedura: Stampare con un controllo WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
