---
title: 'Procedura: Restituisce un risultato di finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: b574a5bbc08d947371837116915c2fc8c13ec81d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357768"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="875ff-102">Procedura: Restituisce un risultato di finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="875ff-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="875ff-103">In questo esempio mostra come recuperare il risultato della finestra di dialogo per una finestra aperta chiamando <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="875ff-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="875ff-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="875ff-104">Example</span></span>  
 <span data-ttu-id="875ff-105">Prima della chiusura di una finestra di dialogo, relativi <xref:System.Windows.Window.DialogResult%2A> deve essere impostata con un <xref:System.Nullable%601> <xref:System.Boolean> che indica come l'utente ha chiuso la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="875ff-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="875ff-106">Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client determinare come è stata chiusa la finestra di dialogo e, di conseguenza, come elaborare il risultato.</span><span class="sxs-lookup"><span data-stu-id="875ff-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="875ff-107"><xref:System.Windows.Window.DialogResult%2A> può essere impostato solo se è stata aperta una finestra chiamando <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="875ff-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="875ff-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="875ff-108">.NET Framework Security</span></span>  
 <span data-ttu-id="875ff-109">La chiamata a <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per usare tutte le finestre e gli eventi input utente senza alcuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="875ff-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
