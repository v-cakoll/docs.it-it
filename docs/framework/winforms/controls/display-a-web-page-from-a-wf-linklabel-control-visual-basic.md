---
title: 'Procedura: Visualizzare una pagina Web da un controllo LinkLabel di Windows Forms (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 1be9ff06e749d14b46946e899c6ffb6c3a950d65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170027"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Procedura: Visualizzare una pagina Web da un controllo LinkLabel di Windows Forms (Visual Basic)
In questo esempio viene visualizzata una pagina Web nel browser predefinito quando un utente fa clic su un form Windows <xref:System.Windows.Forms.LinkLabel> controllo.  
  
## <a name="example"></a>Esempio  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un modulo di Windows denominato `Form1`.  
  
-   Un controllo <xref:System.Windows.Forms.LinkLabel> denominato `LinkLabel1`.  
  
-   Una connessione Internet attiva.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata al <xref:System.Diagnostics.Process.Start%2A> metodo richiede attendibilità totale. Per altre informazioni, vedere <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel>
- [Controllo LinkLabel](linklabel-control-windows-forms.md)
