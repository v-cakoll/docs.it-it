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
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988394"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Accesso ai membri non esposti del Document Object Model HTML gestito
Il codice HTML Document Object Model (Dom) gestito contiene una classe <xref:System.Windows.Forms.HtmlElement> denominata che espone le proprietà, i metodi e gli eventi di tutti gli elementi HTML in comune. In alcuni casi, tuttavia, sarà necessario accedere ai membri non esposti direttamente dall'interfaccia gestita. In questo argomento vengono esaminati due modi per accedere ai membri non esposti, incluse le funzioni JScript e VBScript definite all'interno di una pagina Web.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Accesso ai membri non esposti tramite interfacce gestite  
 <xref:System.Windows.Forms.HtmlDocument>e <xref:System.Windows.Forms.HtmlElement> forniscono quattro metodi che consentono l'accesso ai membri non esposti. La tabella seguente illustra i tipi e i metodi corrispondenti.  
  
|Tipo di membro|Metodo/i|  
|-----------------|-----------------|  
|Proprietà (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Metodi|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|Eventi (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 Quando si usano questi metodi, si presuppone che si disponga di un elemento del tipo sottostante corretto. Si supponga di voler ascoltare l' `Submit` evento di un `FORM` elemento in una pagina HTML, in modo da poter eseguire alcune operazioni di `FORM`pre-elaborazione sui valori di prima che l'utente li invii al server. Idealmente, se si ha il controllo sul codice HTML, è necessario definire `FORM` per avere un attributo `ID` univoco.  
  
```html  
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
  
 Una volta caricata questa pagina nel <xref:System.Windows.Forms.WebBrowser> controllo, è possibile utilizzare il <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> metodo per recuperare `FORM` in fase di esecuzione utilizzando `form1` come argomento.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Accesso a interfacce non gestite  
 È anche possibile accedere ai membri non esposti sul DOM HTML gestito usando le interfacce di Component Object Model non gestite (COM) esposte da ogni classe DOM. Questa operazione è consigliata se è necessario effettuare diverse chiamate a membri non esposti o se i membri non esposti restituiscono altre interfacce non gestite non sottoposte a incapsulamento dal DOM HTML gestito.  
  
 La tabella seguente mostra tutte le interfacce non gestite esposte tramite il DOM HTML gestito. Fare clic su ogni collegamento per una spiegazione dell'utilizzo e per il codice di esempio.  
  
|Type|Interfaccia non gestita|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Il modo più semplice per usare le interfacce COM consiste nell'aggiungere un riferimento alla libreria DOM HTML non gestita (MSHTML. dll) dall'applicazione, anche se questa operazione non è supportata. Per ulteriori informazioni, vedere l' [articolo della Knowledge Base 934368](https://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Accesso alle funzioni di script  
 Una pagina HTML può definire una o più funzioni utilizzando un linguaggio di scripting, ad esempio JScript o VBScript. Queste funzioni vengono posizionate all'interno `SCRIPT` di una pagina della pagina e possono essere eseguite su richiesta o in risposta a un evento nel DOM.  
  
 È possibile chiamare qualsiasi funzione script definita in una pagina HTML usando il <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> metodo. Se il metodo di script restituisce un elemento HTML, è possibile usare un cast per convertire il risultato restituito in <xref:System.Windows.Forms.HtmlElement>un oggetto. Per informazioni dettagliate ed esempi di codice <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>, vedere.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzare il Document Object Model HTML gestito](using-the-managed-html-document-object-model.md)
