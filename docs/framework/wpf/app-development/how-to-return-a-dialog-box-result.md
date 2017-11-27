---
title: 'Procedura: restituire un risultato di casella della finestra di dialogo'
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
helpviewer_keywords: dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5a1b8cdc0544bfba3f708db40e8b9c593b45b35
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="43d00-102">Procedura: restituire un risultato di casella della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="43d00-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="43d00-103">In questo esempio viene illustrato come recuperare il risultato della finestra di dialogo per una finestra che viene aperto chiamando <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="43d00-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43d00-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="43d00-104">Example</span></span>  
 <span data-ttu-id="43d00-105">Prima della chiusura di una finestra di dialogo, il relativo <xref:System.Windows.Window.DialogResult%2A> deve essere impostata con un <xref:System.Nullable%601> <xref:System.Boolean> che indica come viene chiusa la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="43d00-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="43d00-106">Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client determinare la modalità in cui è stata chiusa la finestra di dialogo e, di conseguenza, come elaborare il risultato.</span><span class="sxs-lookup"><span data-stu-id="43d00-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43d00-107"><xref:System.Windows.Window.DialogResult%2A>può essere impostata solo se è stata aperta una finestra chiamando <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="43d00-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="43d00-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="43d00-108">.NET Framework Security</span></span>  
 <span data-ttu-id="43d00-109">La chiamata <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="43d00-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
