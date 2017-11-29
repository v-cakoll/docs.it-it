---
title: 'Procedura: modificare colonne e righe utilizzando ColumnDefinitionsCollection e RowDefinitionsCollection'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e87c5001a676bcda331d289c286cf6b3e87c136f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="77cff-102">Procedura: modificare colonne e righe utilizzando ColumnDefinitionsCollection e RowDefinitionsCollection</span><span class="sxs-lookup"><span data-stu-id="77cff-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="77cff-103">In questo esempio viene illustrato come utilizzare i metodi di <xref:System.Windows.Controls.ColumnDefinitionCollection> e <xref:System.Windows.Controls.RowDefinitionCollection> classi per eseguire azioni quali l'aggiunta, la cancellazione o il conteggio del contenuto di righe o colonne.</span><span class="sxs-lookup"><span data-stu-id="77cff-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="77cff-104">Ad esempio, è possibile <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, o <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> gli elementi inclusi in un <xref:System.Windows.Controls.ColumnDefinition> o <xref:System.Windows.Controls.RowDefinition>.</span><span class="sxs-lookup"><span data-stu-id="77cff-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77cff-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="77cff-105">Example</span></span>  
 <span data-ttu-id="77cff-106">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Grid> elemento con un <xref:System.Windows.FrameworkElement.Name%2A> di `grid1`.</span><span class="sxs-lookup"><span data-stu-id="77cff-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="77cff-107">Il <xref:System.Windows.Controls.Grid> contiene un <xref:System.Windows.Controls.StackPanel> contenente <xref:System.Windows.Controls.Button> elementi, ognuno controllato da un metodo di raccolta diverso.</span><span class="sxs-lookup"><span data-stu-id="77cff-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="77cff-108">Quando fa clic su un <xref:System.Windows.Controls.Button>, viene attivata una chiamata al metodo nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="77cff-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="77cff-109">In questo esempio definisce una serie di metodi personalizzati, ognuno corrispondente a un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span><span class="sxs-lookup"><span data-stu-id="77cff-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="77cff-110">È possibile modificare il numero di colonne e righe di <xref:System.Windows.Controls.Grid> in diversi modi, che include l'aggiunta o rimozione di righe e colonne e il conteggio del numero totale di righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="77cff-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="77cff-111">Per evitare <xref:System.ArgumentOutOfRangeException> e <xref:System.ArgumentException> eccezioni, è possibile utilizzare la funzionalità di controllo degli errori che il <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> metodo fornisce.</span><span class="sxs-lookup"><span data-stu-id="77cff-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="77cff-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77cff-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.ColumnDefinitionCollection>  
 <xref:System.Windows.Controls.RowDefinitionCollection>
