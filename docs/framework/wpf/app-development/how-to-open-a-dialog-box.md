---
title: 'Procedura: aprire una finestra di dialogo'
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
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d318f35f8f009f0f2c77210ca8b6b29bedfb7619
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-dialog-box"></a>Procedura: aprire una finestra di dialogo
In questo esempio viene illustrato come aprire una finestra di dialogo.  
  
## <a name="example"></a>Esempio  
 Una finestra di dialogo è una finestra che viene aperta creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.ShowDialog%2A> metodo. <xref:System.Windows.Window.ShowDialog%2A>Apre una finestra e non restituisce fino a quando non è stata chiusa la finestra di dialogo Nuovo. Questo tipo di finestra è noto anche come un *modale* finestra e limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata <xref:System.Windows.Window.ShowDialog%2A> richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Restituire il risultato di una finestra di dialogo](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
