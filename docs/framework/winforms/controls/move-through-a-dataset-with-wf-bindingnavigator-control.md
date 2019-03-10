---
title: 'Procedura: Esplorare un DataSet con il controllo BindingNavigator di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: d8db965993e82040cfe88c22aaabfaed21462a40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709753"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a>Procedura: Esplorare un DataSet con il controllo BindingNavigator di Windows Form
Durante la creazione di applicazioni basate sui dati, è spesso necessario visualizzare raccolte di dati agli utenti. Il controllo <xref:System.Windows.Forms.BindingNavigator>, unitamente al componente <xref:System.Windows.Forms.BindingSource>, rappresenta una soluzione pratica e versatile per spostarsi all'interno di una raccolta e visualizzare gli elementi in sequenza.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come usare un controllo <xref:System.Windows.Forms.BindingNavigator> per spostarsi all'interno dei dati. Il set è contenuto in una classe <xref:System.Data.DataView>, associata a un controllo <xref:System.Windows.Forms.TextBox> con un componente <xref:System.Windows.Forms.BindingSource>.  
  
> [!NOTE]
>  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Data, System.Drawing, System.Windows.Forms e System.Xml.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Componente BindingSource](bindingsource-component.md)
- [Procedura: Associare un controllo di Windows Form a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
