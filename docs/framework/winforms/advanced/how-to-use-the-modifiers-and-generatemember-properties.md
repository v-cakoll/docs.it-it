---
title: "Procedura: utilizzare modificatori e proprietà GenerateMember"
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
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f11595daac74ceb76c5d017af015d5523506bdf3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>Procedura: utilizzare modificatori e proprietà GenerateMember
Quando si inserisce un componente in un Windows Form, due proprietà sono fornite dall'ambiente di progettazione: `GenerateMember` e `Modifiers`. Il `GenerateMember` proprietà consente di specificare quando la finestra di progettazione Windows Form genera una variabile membro per un componente. Il `Modifiers` proprietà è il modificatore di accesso assegnato a tale variabile membro. Se il valore della `GenerateMember` proprietà `false`, il valore della `Modifiers` proprietà non ha alcun effetto.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a>Per specificare se un componente è un membro del modulo  
  
1.  In Progettazione Windows Form, aprire il form.  
  
2.  Aprire il **della casella degli strumenti**e nel form, inserire tre <xref:System.Windows.Forms.Button> controlli.  
  
3.  Impostare il `GenerateMember` e `Modifiers` proprietà per ogni <xref:System.Windows.Forms.Button> controllo in base alla tabella seguente.  
  
    |Nome pulsante|Valore di GenerateMember|Valore di Modifiers|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|Nessuna modifica|  
  
4.  Compilare la soluzione.  
  
5.  In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.  
  
6.  Aprire il **Form1** nodo e il **Editor di codice**, aprire il **Form1** o **Form1. Designer.cs** file. Questo file contiene il codice generato da Progettazione Windows Form.  
  
7.  Trovare le dichiarazioni per tre pulsanti. Esempio di codice seguente mostra le differenze specificate dal `GenerateMember` e `Modifiers` proprietà.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  Per impostazione predefinita, Progettazione Windows Form viene assegnato il `private` (`Friend` in Visual Basic) per i controlli contenitore come modificatore di <xref:System.Windows.Forms.Panel>. Se la base <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> dispone di un controllo contenitore, non verranno accettati nuovi elementi figlio nei moduli e dei controlli ereditati. La soluzione consiste nel modificare il modificatore del controllo contenitore di base per `protected` o `public`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Button>  
 [Ereditarietà visiva di Windows Form](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Procedura dettagliata: dimostrazione dell'ereditarietà visiva](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [Procedura: ereditare Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
