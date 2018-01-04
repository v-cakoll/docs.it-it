---
title: 'Procedura: ottenere tutte le finestre in un''applicazione'
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
helpviewer_keywords: window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fdb1baad8b779b6ef0443a05e5f6575b552b1c19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-all-windows-in-an-application"></a>Procedura: ottenere tutte le finestre in un'applicazione
In questo esempio viene illustrato come ottenere tutti <xref:System.Windows.Window> oggetti in un'applicazione.  
  
## <a name="example"></a>Esempio  
 Ogni creazione di un'istanza <xref:System.Windows.Window> dell'oggetto, se visibile oppure No, viene automaticamente aggiunto a una raccolta di riferimenti di finestre che è gestito da <xref:System.Windows.Application>ed esposto da <xref:System.Windows.Application.Windows%2A>.  
  
 È possibile enumerare <xref:System.Windows.Application.Windows%2A> per ottenere tutte le istanze di windows utilizzando il codice seguente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
