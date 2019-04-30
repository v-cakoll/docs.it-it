---
title: 'Procedura: Aprire una finestra'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947680"
---
# <a name="how-to-open-a-window"></a>Procedura: Aprire una finestra
In questo esempio viene illustrato come aprire una finestra.  
  
## <a name="example"></a>Esempio  
 Viene aperta una finestra creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.Show%2A> (metodo). <xref:System.Windows.Window.Show%2A> Apre una finestra e viene restituito immediatamente senza attendere che la nuova finestra da chiudere. Questo tipo di finestra è noto anche come un *modale* finestra e non limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Creazione di un'istanza <xref:System.Windows.Window> richiede l'autorizzazione per chiamare i metodi nativi non sicuri (vedere <xref:System.Windows.Window.%23ctor%2A>).
