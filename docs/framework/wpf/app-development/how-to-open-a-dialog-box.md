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
# <a name="how-to-open-a-dialog-box"></a>Procedura: Aprire una finestra di dialogo
In questo esempio viene illustrato come aprire una finestra di dialogo.  
  
## <a name="example"></a>Esempio  
 Una finestra di dialogo è una finestra che viene aperta creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.ShowDialog%2A> (metodo). <xref:System.Windows.Window.ShowDialog%2A> Apre una finestra e non viene restituita finché la nuova finestra di dialogo è stata chiusa. Questo tipo di finestra è noto anche come un *modale* finestra e limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata a <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per usare tutte le finestre e gli eventi input utente senza alcuna restrizione.  
  
## <a name="see-also"></a>Vedere anche

- [Restituire il risultato di una finestra di dialogo](how-to-return-a-dialog-box-result.md)
