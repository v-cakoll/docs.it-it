---
title: 'Procedura: Restituire il risultato di una finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: b574a5bbc08d947371837116915c2fc8c13ec81d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006708"
---
# <a name="how-to-return-a-dialog-box-result"></a>Procedura: Restituire il risultato di una finestra di dialogo
In questo esempio mostra come recuperare il risultato della finestra di dialogo per una finestra aperta chiamando <xref:System.Windows.Window.ShowDialog%2A>.  
  
## <a name="example"></a>Esempio  
 Prima della chiusura di una finestra di dialogo, relativi <xref:System.Windows.Window.DialogResult%2A> deve essere impostata con un <xref:System.Nullable%601> <xref:System.Boolean> che indica come l'utente ha chiuso la finestra di dialogo. Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client determinare come è stata chiusa la finestra di dialogo e, di conseguenza, come elaborare il risultato.  
  
> [!NOTE]
>  <xref:System.Windows.Window.DialogResult%2A> può essere impostato solo se è stata aperta una finestra chiamando <xref:System.Windows.Window.ShowDialog%2A>.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata a <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per usare tutte le finestre e gli eventi input utente senza alcuna restrizione.
