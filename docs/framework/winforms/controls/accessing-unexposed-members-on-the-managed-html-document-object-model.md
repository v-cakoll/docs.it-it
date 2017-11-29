---
title: Accesso ai membri non esposti del Document Object Model HTML gestito
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
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dda2581ceed854fa5121076f0c7b9df414bffe52
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Accesso ai membri non esposti del Document Object Model HTML gestito
Il documento oggetto Model (DOM) HTML gestito contiene una classe denominata <xref:System.Windows.Forms.HtmlElement> che espone proprietà, metodi ed eventi che hanno in comune di tutti gli elementi HTML. In alcuni casi, tuttavia, è necessario accedere ai membri dell'interfaccia gestita non espone direttamente. In questo argomento esamina due modalità per l'accesso a membri non esposti, tra cui [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] funzioni e VBScript definite all'interno di una pagina Web.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>L'accesso ai membri non esposti tramite le interfacce gestite  
 <xref:System.Windows.Forms.HtmlDocument>e <xref:System.Windows.Forms.HtmlElement> forniscono quattro metodi che consentono l'accesso a membri non esposti. La tabella seguente illustra i tipi e i relativi metodi.  
  
|Tipo di membro|O più metodi|  
|-----------------|-----------------|  
|Proprietà (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Metodi|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Quando si utilizzano questi metodi, si presuppone la presenza di un elemento del tipo sottostante corretto. Si supponga che si desidera ascoltare il `Submit` evento di un `FORM` elemento HTML di pagina, in modo che è possibile eseguire alcune operazioni di pre-elaborazione di `FORM`del valori prima che l'utente li invia al server. In teoria, se si dispone di controllo HTML, definire il `FORM` avere univoco `ID` attributo.  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 Dopo il caricamento della pagina nel <xref:System.Windows.Forms.WebBrowser> (controllo), è possibile utilizzare il <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> metodo per recuperare il `FORM` in fase di esecuzione utilizzando `form1` come argomento.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>L'accesso a interfacce non gestite  
 È anche possibile accedere a membri non esposti nel DOM HTML gestito tramite le interfacce componente COM (Object Model) non gestite esposte da ogni classe DOM. Questo è consigliabile se è necessario eseguire varie chiamate a membri non esposti o se i membri non esposti restituiscono altre interfacce non gestite non sottoposto a wrapping da DOM. HTML gestito  
  
 Nella tabella seguente mostra tutte le interfacce non gestite esposte tramite DOM. HTML gestito Fare clic su ogni collegamento per una spiegazione dell'utilizzo e, ad esempio codice.  
  
|Tipo|Interfaccia non gestita|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Il modo più semplice per utilizzare le interfacce COM è per aggiungere un riferimento alla libreria DOM HTML (Mshtml. dll) non gestita dall'applicazione, anche se ciò non è supportata. Per ulteriori informazioni, vedere [934368 articolo della Knowledge Base](http://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Funzioni di Script di accesso  
 Una pagina HTML è possibile definire una o più funzioni tramite un linguaggio di scripting, ad esempio [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] o VBScript. Queste funzioni vengono posizionate all'interno di un `SCRIPT` nella pagina e può essere eseguito su richiesta o in risposta a un evento nel DOM.  
  
 È possibile chiamare qualsiasi funzione di script definita in una pagina HTML utilizzando il <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> metodo. Se il metodo di script restituisce un elemento HTML, è possibile utilizzare un cast per convertire il risultato in un <xref:System.Windows.Forms.HtmlElement>. Per informazioni dettagliate e codice di esempio, vedere <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzare il Document Object Model HTML gestito](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
