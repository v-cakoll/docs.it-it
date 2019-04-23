---
title: Modifica della selezione a livello di codice in un oggetto RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: b8acfe7cde1fe5dae96cd6324f75c5b146be9ec9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096226"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="7a3ad-102">Modifica della selezione a livello di codice in un oggetto RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7a3ad-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="7a3ad-103">In questo esempio viene illustrato come modificare a livello di codice la selezione corrente in un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="7a3ad-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="7a3ad-104">Questa selezione è lo stesso come se l'utente ha selezionato il contenuto usando l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="7a3ad-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a3ad-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a3ad-105">Example</span></span>  
 <span data-ttu-id="7a3ad-106">Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice descrive un oggetto denominato <xref:System.Windows.Controls.RichTextBox> controllo con contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="7a3ad-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="7a3ad-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a3ad-107">Example</span></span>  
 <span data-ttu-id="7a3ad-108">Il codice seguente a livello di codice consente di selezionare testo arbitrario quando l'utente fa clic all'interno di <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="7a3ad-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7a3ad-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a3ad-109">See also</span></span>

- [<span data-ttu-id="7a3ad-110">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7a3ad-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="7a3ad-111">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="7a3ad-111">TextBox Overview</span></span>](textbox-overview.md)
