---
title: 'Procedura: Aprire una finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084987"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="2378d-102">Procedura: Aprire una finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="2378d-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="2378d-103">In questo esempio viene illustrato come aprire una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2378d-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2378d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2378d-104">Example</span></span>  
 <span data-ttu-id="2378d-105">Una finestra di dialogo è una finestra che viene aperta creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.ShowDialog%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="2378d-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="2378d-106"><xref:System.Windows.Window.ShowDialog%2A> Apre una finestra e non viene restituita finché la nuova finestra di dialogo è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="2378d-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="2378d-107">Questo tipo di finestra è noto anche come un *modale* finestra e limita l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2378d-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="2378d-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2378d-108">.NET Framework Security</span></span>  
 <span data-ttu-id="2378d-109">La chiamata a <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per usare tutte le finestre e gli eventi input utente senza alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="2378d-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2378d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2378d-110">See also</span></span>

- [<span data-ttu-id="2378d-111">Restituire il risultato di una finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="2378d-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
