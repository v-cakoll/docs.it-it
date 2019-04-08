---
title: 'Procedura: Associare un controllo ListBox ai dati'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106438"
---
# <a name="how-to-bind-a-listbox-to-data"></a>Procedura: Associare un controllo ListBox ai dati
Uno sviluppatore di applicazioni può creare <xref:System.Windows.Controls.ListBox> controlli senza specificare il contenuto della ognuno <xref:System.Windows.Controls.ListBoxItem> separatamente. È possibile utilizzare l'associazione dati per associare i dati per i singoli elementi.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.ListBox> che consente di popolare il <xref:System.Windows.Controls.ListBoxItem> elementi in base al data binding a un'origine dati denominata *colori*. In questo caso non è necessario usare <xref:System.Windows.Controls.ListBoxItem> tag per specificare il contenuto di ogni elemento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [Controlli](../advanced/optimizing-performance-controls.md)
