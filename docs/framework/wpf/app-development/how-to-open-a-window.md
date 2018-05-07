---
title: 'Procedura: aprire una finestra'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 23dc74666d8f47a0fb735d96ad22ed56c96bdbc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-open-a-window"></a>Procedura: aprire una finestra
In questo esempio viene illustrato come aprire una finestra.  
  
## <a name="example"></a>Esempio  
 Viene aperta una finestra creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.Show%2A> metodo. <xref:System.Windows.Window.Show%2A> verrà visualizzata una finestra e viene restituito immediatamente senza attendere la chiusura della finestra Nuovo. Questo tipo di finestra è noto anche come un *non modale* finestra e non limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Creazione di un'istanza <xref:System.Windows.Window> richiede l'autorizzazione per chiamare metodi nativi unsafe (vedere <xref:System.Windows.Window.%23ctor%2A>).
