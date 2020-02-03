---
title: Visualizza pagina Web dal controllo LinkLabel (Visual Basic)
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
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745922"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Procedura: visualizzare una pagina Web da un controllo LinkLabel di Windows Form (Visual Basic)
In questo esempio viene visualizzata una pagina Web nel browser predefinito quando un utente fa clic su un controllo Windows Forms <xref:System.Windows.Forms.LinkLabel>.  
  
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
  
- Windows Form denominato `Form1`.  
  
- Un controllo <xref:System.Windows.Forms.LinkLabel> denominato `LinkLabel1`.  
  
- Una connessione Internet attiva.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata al metodo <xref:System.Diagnostics.Process.Start%2A> richiede l'attendibilità totale. Per altre informazioni, vedere <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel>
- [Controllo LinkLabel](linklabel-control-windows-forms.md)
