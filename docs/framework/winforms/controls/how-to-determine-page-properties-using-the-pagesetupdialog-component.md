---
title: "Procedura: definire le proprietà della pagina con il componente PageSetupDialog"
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
- cpp
helpviewer_keywords:
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a84bb33b147ce25a8d75ce2a7d42e177b1464a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a>Procedura: definire le proprietà della pagina con il componente PageSetupDialog
Il componente [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) presenta layout, dimensioni del foglio e altre opzioni relative al layout di pagina per un documento.  
  
 È necessario specificare un'istanza della classe <xref:System.Drawing.Printing.PrintDocument> , che rappresenta il documento da stampare. È inoltre necessario che sul computer dell'utente sia installata una stampante, locale o di rete, tramite la quale il componente <xref:System.Windows.Forms.PageSetupDialog> determina in parte le scelte di formattazione della pagina presentate all'utente.  
  
 Un aspetto importante dell'uso del componente <xref:System.Windows.Forms.PageSetupDialog> è dato dalla modalità di interazione con la classe <xref:System.Drawing.Printing.PageSettings> . La classe <xref:System.Drawing.Printing.PageSettings> viene usata per specificare le impostazioni che modificano la modalità di stampa di una pagina, come l'orientamento, le dimensioni e i margini. Ciascuna di queste impostazioni è rappresentata come una proprietà della classe <xref:System.Drawing.Printing.PageSettings> . La classe <xref:System.Windows.Forms.PageSetupDialog> modifica i valori delle proprietà per una determinata istanza della classe <xref:System.Drawing.Printing.PageSettings> , che è associata al documento ed è rappresentata come proprietà <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> .  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a>Per impostare le proprietà della pagina mediante il componente PageSetupDialog  
  
1.  Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.  
  
     Nell'esempio seguente il gestore eventi <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> apre un'istanza del componente <xref:System.Windows.Forms.PageSetupDialog> . Un documento esistente è specificato nella proprietà <xref:System.Windows.Forms.PageSetupDialog.Document%2A> e la relativa proprietà <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> è impostata su `false`.  
  
     Nell'esempio si presuppone il modulo contiene un <xref:System.Windows.Forms.Button> (controllo), un <xref:System.Drawing.Printing.PrintDocument> componente denominato `myDocument`e un <xref:System.Windows.Forms.PageSetupDialog> componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew   
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [Procedura: Creare processi di stampa standard per Windows Form](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [Componente PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
