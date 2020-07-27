---
title: Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
description: Vedere un esempio di come aggiungere contenuto a una casella di testo a riga singola usando l'automazione interfaccia utente di Microsoft in .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 4136d460de7091a515580cade16f06e54699727a
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166920"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="8abb7-103">Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8abb7-103">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="8abb7-104">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8abb7-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8abb7-105">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8abb7-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8abb7-106">Questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per inserire testo in una casella di testo a riga singola.</span><span class="sxs-lookup"><span data-stu-id="8abb7-106">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="8abb7-107">Viene fornito un metodo alternativo per controlli con più righe e testo RTF in cui [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="8abb7-107">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="8abb7-108">A scopo di confronto, l'esempio illustra anche come usare i metodi Win32 per ottenere gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="8abb7-108">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8abb7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8abb7-109">Example</span></span>  
 <span data-ttu-id="8abb7-110">Nell'esempio seguente viene illustrata una sequenza di controlli di testo in un'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8abb7-110">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="8abb7-111">Ogni controllo testo viene testato per verificare se è <xref:System.Windows.Automation.ValuePattern> possibile ottenere un oggetto utilizzando il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="8abb7-111">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="8abb7-112">Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern> , <xref:System.Windows.Automation.ValuePattern.SetValue%2A> viene usato il metodo per inserire una stringa definita dall'utente nel controllo di testo.</span><span class="sxs-lookup"><span data-stu-id="8abb7-112">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="8abb7-113">In caso contrario, <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> viene utilizzato il metodo.</span><span class="sxs-lookup"><span data-stu-id="8abb7-113">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="8abb7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8abb7-114">See also</span></span>

- <span data-ttu-id="8abb7-115">[Esempio di testo di inserimento TextPattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8abb7-115">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>
