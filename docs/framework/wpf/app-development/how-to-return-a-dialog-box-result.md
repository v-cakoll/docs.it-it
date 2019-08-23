---
title: 'Procedura: Restituire il risultato di una finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968238"
---
# <a name="how-to-return-a-dialog-box-result"></a>Procedura: Restituire il risultato di una finestra di dialogo
Questo esempio Mostra come recuperare il risultato della finestra di <xref:System.Windows.Window.ShowDialog%2A>dialogo per una finestra aperta chiamando.  
  
## <a name="example"></a>Esempio  
 Prima della chiusura di una finestra di <xref:System.Windows.Window.DialogResult%2A> dialogo, la relativa proprietà deve <xref:System.Nullable%601> essere impostata con un <xref:System.Boolean> valore che indica il modo in cui l'utente ha chiuso la finestra di dialogo. Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client di determinare la modalità di chiusura della finestra di dialogo e, di conseguenza, come elaborare il risultato.  
  
> [!NOTE]
> <xref:System.Windows.Window.DialogResult%2A>può essere impostato solo se una finestra è stata aperta <xref:System.Windows.Window.ShowDialog%2A>chiamando.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La <xref:System.Windows.Window.ShowDialog%2A> chiamata a richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.
