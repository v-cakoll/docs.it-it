---
title: 'Procedura: Cambiare la proprietà FlowDirection del contenuto a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: 97a64ad54384077a15a643dc528d043b2ef6627a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543406"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="6c014-102">Procedura: Cambiare la proprietà FlowDirection del contenuto a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6c014-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="6c014-103">In questo esempio viene illustrato come modificare a livello di codice il <xref:System.Windows.FrameworkElement.FlowDirection%2A> proprietà di un <xref:System.Windows.Controls.FlowDocumentReader>.</span><span class="sxs-lookup"><span data-stu-id="6c014-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c014-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c014-104">Example</span></span>  
 <span data-ttu-id="6c014-105">Due <xref:System.Windows.Controls.Button> vengono creati gli elementi, ognuno dei quali rappresenta uno dei valori possibili di <xref:System.Windows.FlowDirection>.</span><span class="sxs-lookup"><span data-stu-id="6c014-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="6c014-106">Quando un pulsante, il valore della proprietà associata viene applicato al contenuto di un <xref:System.Windows.Controls.FlowDocumentReader> denominato `tf1`.</span><span class="sxs-lookup"><span data-stu-id="6c014-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="6c014-107">Il valore della proprietà viene anche scritto per una <xref:System.Windows.Controls.TextBlock> denominato `txt1`.</span><span class="sxs-lookup"><span data-stu-id="6c014-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="6c014-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c014-108">Example</span></span>  
 <span data-ttu-id="6c014-109">Gli eventi associati i clic sui pulsanti definiti in precedenza vengono gestiti in un file code-behind c#.</span><span class="sxs-lookup"><span data-stu-id="6c014-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
