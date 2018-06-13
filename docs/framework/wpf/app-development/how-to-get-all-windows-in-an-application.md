---
title: "Procedura: ottenere tutte le finestre in un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 476905899f5f7d573a16ba876c72f28ea34bbf9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545491"
---
# <a name="how-to-get-all-windows-in-an-application"></a>Procedura: ottenere tutte le finestre in un'applicazione
In questo esempio viene illustrato come ottenere tutti <xref:System.Windows.Window> oggetti in un'applicazione.  
  
## <a name="example"></a>Esempio  
 Ogni creazione di un'istanza <xref:System.Windows.Window> dell'oggetto, se visibile oppure No, viene automaticamente aggiunto a una raccolta di riferimenti di finestre che è gestito da <xref:System.Windows.Application>ed esposto da <xref:System.Windows.Application.Windows%2A>.  
  
 È possibile enumerare <xref:System.Windows.Application.Windows%2A> per ottenere tutte le istanze di windows utilizzando il codice seguente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
