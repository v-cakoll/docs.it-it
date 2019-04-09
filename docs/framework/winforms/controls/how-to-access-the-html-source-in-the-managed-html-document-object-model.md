---
title: "Procedura: Accedere all'origine HTML nel Document Object Model HTML gestito"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 98341270ffdb7788aa5c2713682d7d836bde220e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203262"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>Procedura: Accedere all'origine HTML nel Document Object Model HTML gestito
Le proprietà <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> r <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> del controllo <xref:System.Windows.Forms.WebBrowser> restituiscono l'HTML del documento corrente come si presentava al momento della visualizzazione iniziale. Se tuttavia si modifica la pagina con chiamate a metodo e proprietà, ad esempio <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> e <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, queste modifiche non saranno visualizzate quando si chiama <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> e <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>. Per ottenere l'origine HTML più recente del DOM, è necessario chiamare la proprietà <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> sull'elemento HTML.  
  
 La procedura seguente mostra come recuperare l'origine dinamica e visualizzarla in un menu di scelta rapida separato.  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>Recupero dell'origine dinamica con la proprietà OuterHtml  
  
1.  Creare una nuova applicazione Windows Forms. Iniziare con una sola <xref:System.Windows.Forms.Form>e chiamarlo `Form1`.  
  
2.  Host di <xref:System.Windows.Forms.WebBrowser> controllo nell'applicazione Windows Forms e denominarlo `WebBrowser1`. Per altre informazioni, vedere [Procedura: Aggiungere funzionalità del Browser Web a un'applicazione di Windows Forms](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Creare una seconda <xref:System.Windows.Forms.Form> nell'applicazione denominata `CodeForm`.  
  
4.  Aggiungere un <xref:System.Windows.Forms.RichTextBox> il controllo a `CodeForm` e impostare relativo <xref:System.Windows.Forms.Control.Dock%2A> proprietà `Fill`.  
  
5.  Creare una proprietà pubblica sul `CodeForm` chiamato `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Aggiungere un <xref:System.Windows.Forms.Button> controllo denominato `Button1` per il <xref:System.Windows.Forms.Form>e il monitoraggio per il <xref:System.Windows.Forms.Control.Click> evento. Per informazioni dettagliate sul monitoraggio degli eventi, vedere [eventi](../../../standard/events/index.md).  
  
7.  Aggiungere il codice seguente al gestore eventi <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[DisplayWebBrowserCode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Verificare sempre il valore di <xref:System.Windows.Forms.WebBrowser.Document%2A> prima di tentarne il recupero. Se il caricamento della pagina corrente non viene completato, è possibile che l'inizializzazione di <xref:System.Windows.Forms.WebBrowser.Document%2A> o di uno o più dei relativi oggetti figlio non sia eseguita.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzare il Document Object Model HTML gestito](using-the-managed-html-document-object-model.md)
- [Cenni preliminari sul controllo WebBrowser](webbrowser-control-overview.md)
