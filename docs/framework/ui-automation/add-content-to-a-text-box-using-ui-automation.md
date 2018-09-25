---
title: Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 7c4772d36a88dfede04f7592c1cab776ddcd7d7d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084358"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="16e6a-102">Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="16e6a-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="16e6a-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="16e6a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="16e6a-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="16e6a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="16e6a-105">In questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] inserire testo in una casella di testo a riga singola.</span><span class="sxs-lookup"><span data-stu-id="16e6a-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="16e6a-106">Viene fornito un metodo alternativo per i controlli di testo multilinea e accattivanti in cui [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="16e6a-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="16e6a-107">Ai fini del confronto, l'esempio illustra anche come usare i metodi Win32 per ottenere gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="16e6a-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16e6a-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="16e6a-108">Example</span></span>  
 <span data-ttu-id="16e6a-109">La procedura di esempio seguente con una sequenza di controlli di testo in un'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16e6a-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="16e6a-110">Ogni controllo di testo viene testato per verificare se un <xref:System.Windows.Automation.ValuePattern> oggetto può essere ottenuto da quest'ultimo usando il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="16e6a-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="16e6a-111">Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern>, il <xref:System.Windows.Automation.ValuePattern.SetValue%2A> metodo viene utilizzato per inserire una stringa definita dall'utente nel controllo di testo.</span><span class="sxs-lookup"><span data-stu-id="16e6a-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="16e6a-112">In caso contrario, il <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> viene usato il metodo.</span><span class="sxs-lookup"><span data-stu-id="16e6a-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="16e6a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16e6a-113">See Also</span></span>  
 [<span data-ttu-id="16e6a-114">TextPattern Insert Text Sample</span><span class="sxs-lookup"><span data-stu-id="16e6a-114">TextPattern Insert Text Sample</span></span>](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
