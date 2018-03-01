---
title: 'Procedura: visualizzare una pagina Web da un controllo LinkLabel di Windows Form (Visual Basic)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba5ba3b29bab148087e0f8b80b3f1c43aa74e761
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Procedura: visualizzare una pagina Web da un controllo LinkLabel di Windows Form (Visual Basic)
In questo esempio viene visualizzata una pagina Web nel browser predefinito quando un utente fa clic su un Windows Form <xref:System.Windows.Forms.LinkLabel> controllo.  
  
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
  
-   Un Windows Form denominato `Form1`.  
  
-   Un controllo <xref:System.Windows.Forms.LinkLabel> denominato `LinkLabel1`.  
  
-   Una connessione Internet attiva.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata al <xref:System.Diagnostics.Process.Start%2A> metodo richiede l'attendibilità totale. Per altre informazioni, vedere <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.LinkLabel>  
 [Controllo LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
