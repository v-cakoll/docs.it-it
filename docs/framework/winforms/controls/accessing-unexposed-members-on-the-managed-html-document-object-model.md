---
title: Accesso ai membri non esposti del Document Object Model HTML gestito
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 8767ef0fb484d43ffad4888affebb9d6bb74cc3a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43806017"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Accesso ai membri non esposti del Document Object Model HTML gestito
Il documento oggetto Model (DOM) HTML gestito contiene una classe denominata <xref:System.Windows.Forms.HtmlElement> che espone le proprietà, metodi ed eventi che hanno in comune di tutti gli elementi HTML. In alcuni casi, tuttavia, è necessario accedere ai membri che l'interfaccia gestita non espone direttamente. In questo argomento esamina due modi per l'accesso a membri non esposti, tra cui [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] e le funzioni VBScript definite all'interno di una pagina Web.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>L'accesso ai membri non esposti tramite interfacce gestite  
 <xref:System.Windows.Forms.HtmlDocument> e <xref:System.Windows.Forms.HtmlElement> forniscono quattro metodi che consentono l'accesso ai membri non esposti. Nella tabella seguente illustra i tipi e i relativi metodi.  
  
|Tipo di membro|Metodi|  
|-----------------|-----------------|  
|Proprietà (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Metodi|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Quando si utilizzano questi metodi, si presuppone che si dispone di un elemento del tipo sottostante corretto. Si supponga che si desidera essere in ascolto per il `Submit` eventi di un `FORM` pagina elemento in un elemento HTML, in modo che sia possibile eseguire alcune operazioni di pre-elaborazione nel `FORM`del valori prima che l'utente li invia al server. In teoria, è possibile controllare il codice HTML, è possibile definire le `FORM` per avere un valore univoco `ID` attributo.  
  
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
  
 Dopo il caricamento della pagina nel <xref:System.Windows.Forms.WebBrowser> (controllo), è possibile usare il <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> metodo per recuperare le `FORM` in fase di esecuzione tramite `form1` come argomento.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>L'accesso a interfacce non gestite  
 È anche possibile accedere membri non esposti del DOM HTML gestito tramite le interfacce non gestite modello COM (Component Object) esposte da ogni classe DOM. Ciò è consigliabile se è necessario effettuare diverse chiamate con membri non esposti, o se i membri non esposti restituiscano altre interfacce non gestite non integrate in DOM. HTML gestito  
  
 Nella tabella seguente mostra tutte le interfacce non gestite esposte tramite DOM. HTML gestito Fare clic su ogni collegamento per una spiegazione dell'utilizzo e, ad esempio codice.  
  
|Tipo|Interfaccia non gestita|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Il modo più semplice per usare le interfacce COM consiste nell'aggiungere un riferimento alla libreria DOM HTML (Mshtml. dll) non gestita dall'applicazione, anche se ciò non è supportata. Per altre informazioni, vedere [934368 articolo della Knowledge Base](https://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>L'accesso a funzioni di Script  
 Una pagina HTML può definire una o più funzioni con un linguaggio di scripting, ad esempio [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] o VBScript. Queste funzioni vengono posizionate all'interno di un `SCRIPT` nella pagina e può essere eseguito su richiesta o in risposta a un evento in DOM.  
  
 È possibile chiamare qualsiasi funzione di script è definita in una pagina HTML utilizzando la <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> (metodo). Se il metodo di script restituisce un elemento HTML, è possibile usare un cast per convertire il risultato in un <xref:System.Windows.Forms.HtmlElement>. Per dettagli ed esempio di codice, vedere <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzare il Document Object Model HTML gestito](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
