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
ms.openlocfilehash: 432e39efd77a0cf153e3d0287f061702dd3c5c1e
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221004"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="64728-102">Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="64728-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="64728-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="64728-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="64728-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="64728-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="64728-105">In questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] inserire testo in una casella di testo a riga singola.</span><span class="sxs-lookup"><span data-stu-id="64728-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="64728-106">Viene fornito un metodo alternativo per i controlli di testo multilinea e accattivanti in cui [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="64728-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="64728-107">Ai fini del confronto, l'esempio illustra anche come usare i metodi Win32 per ottenere gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="64728-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64728-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="64728-108">Example</span></span>  
 <span data-ttu-id="64728-109">La procedura di esempio seguente con una sequenza di controlli di testo in un'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="64728-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="64728-110">Ogni controllo di testo viene testato per verificare se un <xref:System.Windows.Automation.ValuePattern> oggetto può essere ottenuto da quest'ultimo usando il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="64728-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="64728-111">Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern>, il <xref:System.Windows.Automation.ValuePattern.SetValue%2A> metodo viene utilizzato per inserire una stringa definita dall'utente nel controllo di testo.</span><span class="sxs-lookup"><span data-stu-id="64728-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="64728-112">In caso contrario, il <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> viene usato il metodo.</span><span class="sxs-lookup"><span data-stu-id="64728-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="64728-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64728-113">See also</span></span>
- <span data-ttu-id="64728-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="64728-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>
