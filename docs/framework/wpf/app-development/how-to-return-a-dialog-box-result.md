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
---
# <a name="how-to-return-a-dialog-box-result"></a>Procedura: restituire un risultato di casella della finestra di dialogo
In questo esempio viene illustrato come recuperare il risultato della finestra di dialogo per una finestra che viene aperto chiamando <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Esempio  
 Prima della chiusura di una finestra di dialogo, il relativo <xref:System.Windows.Window.DialogResult%2A> deve essere impostata con un <xref:System.Nullable%601> <xref:System.Boolean> che indica come viene chiusa la finestra di dialogo. Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client determinare la modalità in cui è stata chiusa la finestra di dialogo e, di conseguenza, come elaborare il risultato.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A> può essere impostata solo se è stata aperta una finestra chiamando <xref:System.Windows.Window.ShowDialog%2A>.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.
