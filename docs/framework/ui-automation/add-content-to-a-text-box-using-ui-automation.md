---
title: Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: edc11040a782151af83cb9318ab424426c712e0a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="ecb9f-102">Aggiungere contenuto a una casella di testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="ecb9f-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="ecb9f-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ecb9f-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="ecb9f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ecb9f-105">In questo argomento contiene codice di esempio che illustra come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per inserire testo in una casella di testo a riga singola.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="ecb9f-106">Viene fornito un metodo alternativo per i controlli su più righe e rich text in cui [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="ecb9f-107">Ai fini del confronto, nell'esempio viene inoltre illustrato come utilizzare i metodi Win32 per ottenere gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecb9f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="ecb9f-108">Example</span></span>  
 <span data-ttu-id="ecb9f-109">Nell'esempio seguente in una sequenza di controlli di testo in un'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="ecb9f-110">Ogni controllo di testo viene testato per verificare se un <xref:System.Windows.Automation.ValuePattern> oggetto può essere ottenuto tramite il <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="ecb9f-111">Se il controllo di testo supporta <xref:System.Windows.Automation.ValuePattern>, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> metodo viene utilizzato per inserire una stringa definita dall'utente nel controllo di testo.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="ecb9f-112">In caso contrario, il <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> viene usato il metodo.</span><span class="sxs-lookup"><span data-stu-id="ecb9f-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="ecb9f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecb9f-113">See Also</span></span>  
 [<span data-ttu-id="ecb9f-114">TextPattern Insert Text Sample</span><span class="sxs-lookup"><span data-stu-id="ecb9f-114">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
