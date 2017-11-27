---
title: 'Procedura: aprire una finestra'
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
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6eec13ec1bac864376fcdf5417cc4be68f16dd46
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-window"></a>Procedura: aprire una finestra
In questo esempio viene illustrato come aprire una finestra.  
  
## <a name="example"></a>Esempio  
 Viene aperta una finestra creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.Show%2A> metodo. <xref:System.Windows.Window.Show%2A>Apre una finestra e viene restituito immediatamente senza attendere la chiusura della finestra Nuovo. Questo tipo di finestra è noto anche come un *non modale* finestra e non limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Creazione di un'istanza <xref:System.Windows.Window> richiede l'autorizzazione per chiamare metodi nativi unsafe (vedere <xref:System.Windows.Window.%23ctor%2A>).
