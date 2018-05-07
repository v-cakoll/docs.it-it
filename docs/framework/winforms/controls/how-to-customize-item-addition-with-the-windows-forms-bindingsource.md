---
title: "Procedura: personalizzare l'aggiunta di elementi con BindingSource Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: 299b24eb42c576535389f53982581bf4a776ee3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a>Procedura: personalizzare l'aggiunta di elementi con BindingSource Windows Form
Quando si usa un componente <xref:System.Windows.Forms.BindingSource> per associare un controllo Windows Form a un'origine dati, potrebbe essere necessario personalizzare la creazione di nuovi elementi. Il componente <xref:System.Windows.Forms.BindingSource> semplifica questa attività per mezzo dell'evento <xref:System.Windows.Forms.BindingSource.AddingNew> , che di solito viene generato quando il controllo associato deve creare un nuovo elemento. Il gestore eventi può fornire qualsiasi comportamento personalizzato sia necessario (ad esempio, la chiamata a un metodo su un servizio Web o l'acquisizione di un nuovo oggetto da una class factory).  
  
> [!NOTE]
>  Quando un elemento viene aggiunto gestendo l'evento <xref:System.Windows.Forms.BindingSource.AddingNew> , l'aggiunta non può essere annullata.  
  
## <a name="example"></a>Esempio  
 Il seguente esempio mostra come associare un controllo <xref:System.Windows.Forms.DataGridView> a una class factory usando un componente <xref:System.Windows.Forms.BindingSource> . Quando l'utente fa clic sulla nuova riga del controllo <xref:System.Windows.Forms.DataGridView> , viene generato l'evento <xref:System.Windows.Forms.BindingSource.AddingNew> . Il gestore eventi crea un nuovo oggetto `DemoCustomer`, che viene assegnato alla proprietà <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType>. In questo modo il nuovo oggetto `DemoCustomer` viene aggiunto all'elenco del componente <xref:System.Windows.Forms.BindingSource> e visualizzato nella nuova riga del controllo <xref:System.Windows.Forms.DataGridView> .  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Procedura: Associare un controllo di Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
