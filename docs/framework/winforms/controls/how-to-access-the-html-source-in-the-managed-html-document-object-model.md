---
title: "Procedura: accedere all'origine HTML nel Document Object Model HTML gestito"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 49a50bdf5ea0f24d712458c739b7829ee73d157a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527813"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>Procedura: accedere all'origine HTML nel Document Object Model HTML gestito
Le proprietà <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> r <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del controllo <xref:System.Windows.Forms.WebBrowser> restituiscono l'HTML del documento corrente come si presentava al momento della visualizzazione iniziale. Se tuttavia si modifica la pagina con chiamate a metodo e proprietà, ad esempio <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> e <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, queste modifiche non saranno visualizzate quando si chiama <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> e <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>. Per ottenere l'origine HTML più recente del DOM, è necessario chiamare la proprietà <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> sull'elemento HTML.  
  
 La procedura seguente mostra come recuperare l'origine dinamica e visualizzarla in un menu di scelta rapida separato.  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>Recupero dell'origine dinamica con la proprietà OuterHtml  
  
1.  Creare una nuova applicazione Windows Forms. Iniziare con una sola <xref:System.Windows.Forms.Form>e lo chiama `Form1`.  
  
2.  Host di <xref:System.Windows.Forms.WebBrowser> il controllo nell'applicazione Windows Form e denominarlo `WebBrowser1`. Per ulteriori informazioni, vedere [procedura: aggiungere funzionalità del Browser Web per un'applicazione Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Creare un secondo <xref:System.Windows.Forms.Form> nell'applicazione denominata `CodeForm`.  
  
4.  Aggiungere un <xref:System.Windows.Forms.RichTextBox> il controllo a `CodeForm` e impostare il relativo <xref:System.Windows.Forms.Control.Dock%2A> proprietà `Fill`.  
  
5.  Creare una proprietà pubblica su `CodeForm` chiamato `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Aggiungere un <xref:System.Windows.Forms.Button> controllo denominato `Button1` per il <xref:System.Windows.Forms.Form>e verificare la presenza di <xref:System.Windows.Forms.Control.Click> evento. Per ulteriori informazioni sul monitoraggio degli eventi, vedere [eventi](../../../../docs/standard/events/index.md).  
  
7.  Aggiungere il codice seguente al gestore eventi <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Verificare sempre il valore di <xref:System.Windows.Forms.WebBrowser.Document%2A> prima di tentarne il recupero. Se il caricamento della pagina corrente non viene completato, è possibile che l'inizializzazione di <xref:System.Windows.Forms.WebBrowser.Document%2A> o di uno o più dei relativi oggetti figlio non sia eseguita.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzare il Document Object Model HTML gestito](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 [Panoramica sul controllo WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
