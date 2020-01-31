---
title: Associare il controllo a un tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: 0bc1f92ee8922990bd0e461655168f5618ba39a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744981"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>Procedura: Associare un controllo Windows Form a un tipo
Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo, invece che a un oggetto. Questa situazione si verifica soprattutto in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati a dati devono visualizzare informazioni provenienti dall'interfaccia pubblica di un tipo. Ad esempio, se si associa un controllo <xref:System.Windows.Forms.DataGridView> a un oggetto esposto da un servizio Web, potrebbe essere necessario che in fase di progettazione il controllo <xref:System.Windows.Forms.DataGridView> assegni alle colonne un'etichetta con i nomi dei membri di un tipo personalizzato.  
  
 È possibile associare facilmente un controllo a un tipo con il componente <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="example"></a>Esempio  
 Il seguente esempio di codice mostra come associare un controllo <xref:System.Windows.Forms.DataGridView> a un tipo personalizzato usando un componente <xref:System.Windows.Forms.BindingSource>. Quando si esegue l'esempio, si noterà che le etichette delle colonne di <xref:System.Windows.Forms.DataGridView> rispecchiano le proprietà di un oggetto `Customer`, prima ancora che il controllo venga popolato con i dati. L'esempio contiene un pulsante Add Customer per aggiungere dati al controllo <xref:System.Windows.Forms.DataGridView>. Quando si fa clic sul pulsante, un nuovo oggetto `Customer` viene aggiunto a <xref:System.Windows.Forms.BindingSource>. In uno scenario reale, i dati potrebbero essere ottenuti da una chiamata a un servizio Web o da un'altra origine dati.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Componente BindingSource](bindingsource-component.md)
