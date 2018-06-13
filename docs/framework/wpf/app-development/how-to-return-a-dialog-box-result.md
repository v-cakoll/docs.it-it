---
title: 'Procedura: restituire un risultato di casella della finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 8f754577a355a58060238bbbb487c36aea14658c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545587"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="08723-102">Procedura: restituire un risultato di casella della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="08723-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="08723-103">In questo esempio viene illustrato come recuperare il risultato della finestra di dialogo per una finestra che viene aperto chiamando <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="08723-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08723-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="08723-104">Example</span></span>  
 <span data-ttu-id="08723-105">Prima della chiusura di una finestra di dialogo, il relativo <xref:System.Windows.Window.DialogResult%2A> deve essere impostata con un <xref:System.Nullable%601> <xref:System.Boolean> che indica come viene chiusa la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="08723-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="08723-106">Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client determinare la modalità in cui è stata chiusa la finestra di dialogo e, di conseguenza, come elaborare il risultato.</span><span class="sxs-lookup"><span data-stu-id="08723-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08723-107"><xref:System.Windows.Window.DialogResult%2A> può essere impostata solo se è stata aperta una finestra chiamando <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="08723-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="08723-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="08723-108">.NET Framework Security</span></span>  
 <span data-ttu-id="08723-109">La chiamata <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="08723-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
