---
title: 'Procedura: Modificare colonne e righe utilizzando ColumnDefinitionsCollections e RowDefinitionsCollections'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: c3308f99b8d959b7513c5657d568a18959302aba
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360557"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a>Procedura: Modificare colonne e righe utilizzando ColumnDefinitionsCollections e RowDefinitionsCollections
In questo esempio viene illustrato come utilizzare i metodi di <xref:System.Windows.Controls.ColumnDefinitionCollection> e <xref:System.Windows.Controls.RowDefinitionCollection> classi per eseguire azioni quali l'aggiunta, la cancellazione o il conteggio del contenuto delle righe o colonne. Ad esempio, è possibile <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, o <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> gli elementi inclusi in un <xref:System.Windows.Controls.ColumnDefinition> o <xref:System.Windows.Controls.RowDefinition>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una <xref:System.Windows.Controls.Grid> elemento con un <xref:System.Windows.FrameworkElement.Name%2A> di `grid1`. Il <xref:System.Windows.Controls.Grid> contiene un <xref:System.Windows.Controls.StackPanel> che contiene <xref:System.Windows.Controls.Button> elementi, ognuno controllato da un metodo di raccolta diverso. Quando fa clic su un <xref:System.Windows.Controls.Button>, viene attivata una chiamata al metodo nel file code-behind.  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 In questo esempio definisce una serie di metodi personalizzati, ognuno corrispondente a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file. È possibile modificare il numero di colonne e righe nel <xref:System.Windows.Controls.Grid> in diversi modi, che include aggiungendo o rimuovendo le righe e colonne; e il conteggio del numero totale di righe e colonne. Per impedire <xref:System.ArgumentOutOfRangeException> e <xref:System.ArgumentException> eccezioni, è possibile usare la funzionalità controllo degli errori che il <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> metodo fornisce.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>
